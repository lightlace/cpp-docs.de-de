---
title: 'Vorgehensweise: Verwenden von Safe_cast in c++ / CLI | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f695c45d5202f376a4ce4daf14c37a7fd9a1904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136674"
---
# <a name="how-to-use-safecast-in-ccli"></a>Gewusst wie: Verwenden von safe_cast in C++/CLI
In diesem Artikel wird gezeigt, wie mit "safe_cast" in C + c++ / CLI-Anwendungen. Informationen zu "safe_cast" in [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], finden Sie unter ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md).  
  
## <a name="upcasting"></a>Umwandeln  
 Eine Verallgemeinerung ist eine Umwandlung eines abgeleiteten Typs auf einen der zugehörigen Basisklassen. Diese Umwandlung ist sicher und erfordert keine explizite Umwandlung-Notation. Im folgende Beispiel wird gezeigt, wie eine Typumwandlung nach oben durchführen `safe_cast` und ohne ihn.  
  
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
  
## <a name="downcasting"></a>Downcasting  
 Eine Verweisklasse ist eine Umwandlung von einer Basisklasse in einer Klasse, die von der Basisklasse abgeleitet ist.  Eine Verweisklasse ist threadsicher, nur dann, wenn das Objekt, das zur Laufzeit adressiert ist tatsächlich ein abgeleitetes Klassenobjekt adressiert wird.  Im Gegensatz zu `static_cast`, `safe_cast` eine dynamische Prüfung ausführt und löst <xref:System.InvalidCastException> , wenn die Konvertierung schlägt fehl.  
  
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
 Im folgenden Beispiel wird gezeigt, wie Sie verwenden können `safe_cast` zum Aufrufen von benutzerdefinierten Konvertierungen.  
  
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
  
## <a name="safecast-and-boxing-operations"></a>"safe_cast" und Boxing-Vorgänge  
  
### <a name="boxing"></a>Boxing  
  
 Boxing ist als eine Compiler eingefügter eine benutzerdefinierte Konvertierung definiert.  Aus diesem Grund können Sie `safe_cast` Feld einen Wert auf dem CLR-Heap.  
  
 Das folgende Beispiel zeigt Boxing mit einfachen und benutzerdefinierte Werttypen.  Ein `safe_cast` Felder eine Werttypvariable, die auf den systemeigenen Stapel ist, sodass er auf eine Variable auf dem Garbage collection-Heap zugewiesen werden kann.  
  
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
  
 Das nächste Beispiel veranschaulicht, dass Boxing Priorität über eine benutzerdefinierte Konvertierung in hat ein `safe_cast` Vorgang.  
  
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
  
 Durch Unboxing wird als eine Compiler eingefügter eine benutzerdefinierte Konvertierung definiert.  Aus diesem Grund können Sie `safe_cast` Unboxing ein Werts für die CLR-Heap.  
  
 Eine benutzerdefinierte Konvertierung beim Unboxing handelt, im Gegensatz zu Boxing, unboxing muss jedoch explizit –, also von ausgeführt werden muss eine `static_cast`C- Format umgewandelt, oder `safe_cast`; unboxing kann nicht durchgeführt werden implizit.  
  
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
 Im folgenden Beispiel wird gezeigt, wie Sie verwenden können `safe_cast` auf einer Verweisklasse mit einem generischen Typ durchführen.  
  
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
 ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)