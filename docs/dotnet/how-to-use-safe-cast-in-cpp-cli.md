---
title: 'Vorgehensweise: Verwenden von Safe_cast in C++/CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: 66faadba9530bc7f3c12513277582e405e1b1b34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389085"
---
# <a name="how-to-use-safecast-in-ccli"></a>Vorgehensweise: Verwenden von Safe_cast in C++/CLI

In diesem Artikel wird gezeigt, wie mit "safe_cast" in C++/CLI-Anwendungen. Informationen zu "safe_cast" in C++/CX, finden Sie unter ["safe_cast"](../extensions/safe-cast-cpp-component-extensions.md).

## <a name="upcasting"></a>Umwandeln

Eine Typumwandlung nach oben ist die Umwandlung eines abgeleiteten Typs auf eine ihrer Basisklassen. Diese Umwandlung ist sicher und eine explizite Umwandlungsnotation ist nicht erforderlich. Das folgende Beispiel zeigt, wie Sie eine Typumwandlung nach oben, mit ausführen `safe_cast` und ohne.

```cpp
// safe_upcast.cpp
// compile with: /clr
using namespace System;
interface class A {
   void Test();
};

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test");
   }

   void Test2() {
      Console::WriteLine("in B::Test2");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test");
   };
};

int main() {
   C ^ c = gcnew C;

   // implicit upcast
   B ^ b = c;
   b->Test();
   b->Test2();

   // upcast with safe_cast
   b = nullptr;
   b = safe_cast<B^>(c);
   b->Test();
   b->Test2();
}
```

```Output
in C::Test
in B::Test2
in C::Test
in B::Test2
```

## <a name="downcasting"></a>Typumwandlung

Eine Umwandlung ist eine Umwandlung von einer Basisklasse in eine Klasse, die von der Basisklasse abgeleitet ist.  Eine Umwandlung ist sicher sind, nur, wenn das Objekt, das zur Laufzeit adressiert ist tatsächlich ein abgeleitetes Klassenobjekt richtet.  Im Gegensatz zu `static_cast`, `safe_cast` eine dynamische Prüfung ausführt, und löst eine <xref:System.InvalidCastException> , wenn die Konvertierung schlägt fehl.

```cpp
// safe_downcast.cpp
// compile with: /clr
using namespace System;

interface class A { void Test(); };

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test()");
   }

   void Test2() {
      Console::WriteLine("in B::Test2()");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test()");
   }
};

interface class I {};

value struct V : public I {};

int main() {
   A^ a = gcnew C();
   a->Test();
   B^ b = safe_cast<B^>(a);
   b->Test();
   b->Test2();

   V v;
   I^ i = v;   // i boxes V
   V^ refv = safe_cast<V^>(i);

   Object^ o = gcnew B;
   A^ a2= safe_cast<A^>(o);
}
```

```Output
in C::Test()
in C::Test()
in B::Test2()
```

## <a name="safecast-with-user-defined-conversions"></a>"safe_cast" mit benutzerdefinierten Konvertierungen

Das nächste Beispiel zeigt, wie Sie verwenden können `safe_cast` zum Aufrufen von benutzerdefinierten Konvertierungen.

```cpp
// safe_cast_udc.cpp
// compile with: /clr
using namespace System;
value struct V;

ref struct R {
   int x;
   R() {
      x = 1;
   }

   R(int argx) {
      x = argx;
   }

   static operator R::V^(R^ r);
};

value struct V {
   int x;
   static operator R^(V& v) {
      Console::WriteLine("in operator R^(V& v)");
      R^ r = gcnew R();
      r->x = v.x;
      return r;
   }

   V(int argx) {
      x = argx;
   }
};

   R::operator V^(R^ r) {
      Console::WriteLine("in operator V^(R^ r)");
      return gcnew V(r->x);
   }

int main() {
   bool fReturnVal = false;
   V v(2);
   R^ r = safe_cast<R^>(v);   // should invoke UDC
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC
}
```

```Output
in operator R^(V& v
in operator V^(R^ r)
```

## <a name="safecast-and-boxing-operations"></a>Safe_cast und Boxing-Vorgänge

### <a name="boxing"></a>Boxing

Boxing ist als eine Compiler injizierten, eine benutzerdefinierte Konvertierung definiert.  Aus diesem Grund können Sie `safe_cast` auf das Feld eines Werts auf dem CLR-Heap.

Das folgende Beispiel zeigt die Boxing mit einfachen und benutzerdefinierte Werttypen.  Ein `safe_cast` Felder eine Werttypvariable, die auf den systemeigenen Stapel ist, damit sie eine Variable für die Garbage collection-Heap zugewiesen werden kann.

```cpp
// safe_cast_boxing.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct V : public I {
   int m_x;

   V(int i) : m_x(i) {}
};

int main() {
   // box a value type
   V v(100);
   I^ i = safe_cast<I^>(v);

   int x = 100;
   V^ refv = safe_cast<V^>(v);
   int^ refi = safe_cast<int^>(x);
}
```

Das nächste Beispiel zeigt, dass Boxing höhere Priorität über eine benutzerdefinierte Konvertierung in einen `safe_cast` Vorgang.

```cpp
// safe_cast_boxing_2.cpp
// compile with: /clr
static bool fRetval = true;

interface struct I {};
value struct V : public I {
   int x;

   V(int argx) {
      x = argx;
   }

   static operator I^(V v) {
      fRetval = false;
      I^ pi = v;
      return pi;
   }
};

ref struct R {
   R() {}
   R(V^ pv) {}
};

int main() {
   V v(10);
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"
}
```

### <a name="unboxing"></a>Unboxing

Unboxing wird als eine Compiler injizierten, eine benutzerdefinierte Konvertierung definiert.  Aus diesem Grund können Sie `safe_cast` ein Werts für die CLR-Heap Unboxing zu konvertieren.

Im Gegensatz zu Boxing, unboxing muss jedoch eine benutzerdefinierte Konvertierung beim Unboxing handelt es explizit sein – d. h. durch durchgeführt werden muss eine `static_cast`C- Format umgewandelt, oder `safe_cast`; unboxing kann nicht ausgeführt werden implizit.

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

Das folgende Beispiel zeigt, unboxing mit Werttypen und primitive Typen.

```cpp
// safe_cast_unboxing_2.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct VI : public I {};

void test1() {
   Object^ o = 5;
   int x = safe_cast<Int32>(o);
}

value struct V {
   int x;
   String^ s;
};

void test2() {
   V localv;
   Object^ o = localv;
   V unboxv = safe_cast<V>(o);
}

void test3() {
   V localv;
   V^ o2 = localv;
   V unboxv2 = safe_cast<V>(o2);
}

void test4() {
   I^ refi = VI();
   VI vi  = safe_cast<VI>(refi);
}

int main() {
   test1();
   test2();
   test3();
   test4();
}
```

## <a name="safecast-and-generic-types"></a>Safe_cast und generischen Typen

Das nächste Beispiel zeigt, wie Sie verwenden können `safe_cast` eine Typumwandlung mit einem generischen Typ durchführen.

```cpp
// safe_cast_generic_types.cpp
// compile with: /clr
interface struct I {};

generic<class T> where T:I
ref struct Base {
   T t;
   void test1() {}
};

generic<class T> where T:I
ref struct Derived:public Base <T> {};

ref struct R:public I {};

typedef Base<R^> GBase_R;
typedef Derived<R^> GDerived_R;

int main() {
   GBase_R^ br = gcnew GDerived_R();
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);
}
```

## <a name="see-also"></a>Siehe auch

[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)
