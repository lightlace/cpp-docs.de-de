---
title: "Gewusst wie: Verwenden von safe_cast in C++/CLI"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast-Schlüsselwort [C++], Upcasting"
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von safe_cast in C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird gezeigt, wie safe\_cast in [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]\-Anwendungen.  Informationen zum safe\_cast in [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], finden Sie unter [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
## Upcasting  
 Eine Aufwärtsumwandlung ist eine Typumwandlung von einem abgeleiteten Typ in eine der Basisklassen.  Dadurch, die umgewandelt wird, ist sicher und erfordert keine explizite Umwandlung.  Das folgende Beispiel zeigt, wie eine Aufwärtsumwandlung, mit `safe_cast` und ohne es ausgeführt wird.  
  
```  
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
  
  **in C::Test**  
**in B::Test2**  
**in C::Test**  
**in B::Test2**   
## Downcasting  
 Eine Umwandlung ist eine Typumwandlung von einer Basisklasse zu einer Klasse, die von der Basisklasse abgeleitet ist.  Eine Umwandlung ist sicher, wenn das Objekt, das zur Laufzeit behandelt wird, tatsächlich ein Objekt der abgeleiteten Klasse.  Anders als `static_cast` wird `safe_cast` eine Betriebsprüfung aus und löst <xref:System.InvalidCastException> aus, wenn die Konvertierung fehlschlägt.  
  
```  
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
  
  **in C::Test\(\)**  
**in C::Test\(\)**  
**in B::Test2\(\)**   
## safe\_cast mit benutzerdefinierten Konvertierungen  
 Das folgende Beispiel zeigt, wie Sie `safe_cast` verwenden können, um benutzerdefinierten Konvertierungen aufzurufen.  
  
```  
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
  
  **im Operator R^ \(V & V**  
**im Operator V^ \(R^ r\)**   
## safe\_cast und Boxingvorgänge  
 **Boxing**  
  
 Boxing wird als Compiler\-eingefügte, benutzerdefinierte Konvertierung definiert.  Daher können Sie `safe_cast` verwenden, um einen Wert auf dem CLR\-Heap entfällt.  
  
 Im folgenden Beispiel wird Boxing mit den einfachen und benutzerdefinierten Werttypen aufgeführt.  `safe_cast` packt eine Werttypvariable ein, die auf dem systemeigenen Stapel befindet, damit sie zu einer Variable auf dem Heap der Garbage Collection zugeordnet werden kann.  
  
```  
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
  
 Das folgende Beispiel zeigt, dass das Feld Priorität zu einer benutzerdefinierten Konvertierung in einem `safe_cast` Operation verfügt.  
  
```  
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
  
 **Unboxing**  
  
 Unboxing wird als Compiler\-eingefügte, benutzerdefinierte Konvertierung definiert.  Daher können Sie `safe_cast` verwenden, um einen Wert auf dem CLR\-Heap zu konvertieren.  
  
 Unboxing ist eine benutzerdefinierte Konvertierung, aber anders Boxing, Unboxing, muss EXPLICIT\-dass ist sein, es muss von `static_cast`, wandeln im C\-Format oder `safe_cast` ausgeführt werden; Unboxing kann nicht implizit ausgeführt werden.  
  
```  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 Im folgenden Beispiel wird Unboxing mit Werttypen und primitive Typen an.  
  
```  
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
  
## safe\_cast und generische Typen  
 Das folgende Beispiel zeigt, wie Sie `safe_cast` verwenden können, um eine Umwandlung mit einem generischen Typ auszuführen.  
  
```  
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
  
## Siehe auch  
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)