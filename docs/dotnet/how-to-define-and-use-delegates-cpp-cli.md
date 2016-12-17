---
title: "Gewusst wie: Definieren und Verwenden von Delegaten (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Delegaten"
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Definieren und Verwenden von Delegaten (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird gezeigt, wie Delegaten in [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] definiert und verwendet.  
  
 Obwohl .NET Framework verschiedene Delegaten enthält, manchmal müssen Sie möglicherweise neue Delegaten definieren.  
  
 Das folgende Codebeispiel definiert einen Delegaten, die `MyCallback` genannt wird.  Die Ereignisbehandlungscode\-dfunktion, die aufgerufen wird, wenn dieser neue Delegat ist, ausgelöste\-muss einen Rückgabetyp verfügen `void` und <xref:System.String> einen Verweis verwenden.  
  
 Die Hauptfunktion verwendet eine statische Methode, die von `SomeClass` definiert wird, um den Delegaten `MyCallback` zu instanziieren.  Der Delegat wird anschließend eine alternative Methode zum Aufrufen dieser Funktion, wie dargestellt, indem einzelne" die "Zeichenfolge zum Delegatobjekt sendet.  Nachfolgende, zusätzliche Instanzen von `MyCallback` werden zusammen verknüpft ausgeführt und anschließend durch einen Aufruf an Delegatobjekt.  
  
```  
// use_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
ref class SomeClass  
{  
public:  
   static void Func(String^ str)  
   {  
      Console::WriteLine("static SomeClass::Func - {0}", str);  
   }  
};  
  
ref class OtherClass  
{  
public:  
   OtherClass( Int32 n )   
   {  
      num = n;  
   }  
  
   void Method(String^ str)   
   {  
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",   
         str, num);  
   }  
  
   Int32 num;  
};  
  
delegate void MyCallback(String^ str);  
  
int main( )   
{  
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);     
   callback("single");   
  
   callback += gcnew MyCallback(SomeClass::Func);     
  
   OtherClass^ f = gcnew OtherClass(99);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   f = gcnew OtherClass(100);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   callback("chained");  
  
   return 0;  
}  
```  
  
 **Ausgabe**  
  
  **statisches SomeClass::Func \- sondern Sie aus**  
**statisches SomeClass::Func \- verkettet**  
**statisches SomeClass::Func \- verkettet**  
**OtherClass::Method \- verkettet, numerische \= 99**  
**OtherClass::Method \- verkettet, numerische \= 100** Das folgende Codebeispiel zeigt, wie ein Delegat mit einem Member einer Werteklasse zuordnet.  
  
```  
// mcppv2_del_mem_value_class.cpp  
// compile with: /clr  
using namespace System;  
public delegate void MyDel();  
  
value class A {  
public:  
   void func1() {  
      Console::WriteLine("test");  
   }  
};  
  
int main() {  
   A a;  
   A^ ah = a;  
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a  
   f();  
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);  
   f2();  
}  
```  
  
 **Ausgabe**  
  
  **Testen**  
**Testen**   
## Wie Sie Delegaten erstellt  
 Sie können den Operator "`-`" verwenden, um einen Mithilfe von einem zusammengesetzten Delegaten entfernen.  
  
```  
// mcppv2_compose_delegates.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDelegate(String ^ s);  
  
ref class MyClass {  
public:  
   static void Hello(String ^ s) {  
      Console::WriteLine("Hello, {0}!", s);  
   }  
  
   static void Goodbye(String ^ s) {  
      Console::WriteLine("  Goodbye, {0}!", s);  
   }  
};  
  
int main() {  
  
   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);  
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);  
   MyDelegate ^ c = a + b;  
   MyDelegate ^ d = c - a;  
  
   Console::WriteLine("Invoking delegate a:");  
   a("A");  
   Console::WriteLine("Invoking delegate b:");  
   b("B");  
   Console::WriteLine("Invoking delegate c:");  
   c("C");  
   Console::WriteLine("Invoking delegate d:");  
   d("D");  
}  
```  
  
 **Ausgabe**  
  
  **Aufrufen von Delegaten auf:**  
**Hello\!, A**  
**Aufrufen von Delegaten b:**  
 **goodbye, B\!**  
**Aufrufen von Delegaten c:**  
**Hello\!, C**  
 **goodbye, C\!**  
**Aufrufen von Delegaten d:**  
 **goodbye, D\!**   
## Führen Sie ein delegate^ an eine systemeigene Funktion, die einen Funktionszeiger erwartet  
 Von einer verwalteten Komponente können Sie eine systemeigene Funktion mit Funktionszeigerparametern aufrufen, in denen systemeigene Funktion die Memberfunktion des verwalteten Delegaten der Komponente dann aufrufen kann.  
  
 Dieses Beispiel erstellt die DLL\-, der die systemeigene Funktion exportiert:  
  
```  
// delegate_to_native_function.cpp  
// compile with: /LD  
#include < windows.h >  
extern "C" {  
   __declspec(dllexport)  
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {  
      mgdFunc("Call to Managed Function");  
   }  
}  
```  
  
 Im folgenden Beispiel wird die .dll und übergibt ein Delegathandle die systemeigene Funktion, die einen Funktionszeiger erwartet.  
  
```  
// delegate_to_native_function_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
delegate void Del(String ^s);  
public ref class A {  
public:  
   void delMember(String ^s) {  
      Console::WriteLine(s);  
   }  
};  
  
[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]  
extern "C" void nativeFunction(Del ^d);  
  
int main() {  
   A ^a = gcnew A;  
   Del ^d = gcnew Del(a, &A::delMember);  
   nativeFunction(d);   // Call to native function  
}  
```  
  
 **Ausgabe**  
  
  **Aufruf zur verwalteten Funktion**   
## So Delegaten mit nicht verwalteten Funktionen zuordnen  
 Um einen Delegaten mit einer systemeigenen Funktion zuordnen, müssen Sie die systemeigene Funktion in einem verwalteten Typ umschließen und die durch `PInvoke` aufgerufen werden Funktion deklarieren.  
  
```  
// mcppv2_del_to_umnangd_func.cpp  
// compile with: /clr  
#pragma unmanaged  
extern "C" void printf(const char*, ...);  
class A {  
public:  
   static void func(char* s) {  
      printf(s);  
   }  
};  
  
#pragma managed  
public delegate void func(char*);   
  
ref class B {  
   A* ap;  
  
public:  
   B(A* ap):ap(ap) {}  
   void func(char* s) {  
      ap->func(s);   
   }  
};  
  
int main() {  
   A* a = new A;  
   B^ b = gcnew B(a);  
   func^ f = gcnew func(b, &B::func);  
   f("hello");  
   delete a;  
}  
```  
  
 **Ausgabe**  
  
  **Hello**   
## So fügen Sie ungebundene Delegaten verwenden  
 Sie können einem ungebundenen Delegaten, um eine Instanz des Typs zu übergeben, dessen Funktion Sie aufrufen möchten, wenn der Delegat aufgerufen wird.  
  
 Ungebundene Delegaten sind besonders nützlich, wenn Sie die Objekte in einer Auflistung\-durch die Verwendung von [for each, in](../dotnet/for-each-in.md) durchlaufen Schlüsselwort\- und eine Memberfunktion auf jeder Instanz aufrufen möchten.  
  
 Im Folgenden, wie sowohl Ungebunden Delegaten deklariert, instanziiert und aufgerufen wird:  
  
|Aktion|Grenzen\-Delegaten|Ungebundene Delegaten|  
|------------|------------------------|---------------------------|  
|Declare|Die Signatur muss mit der Signatur der Funktion übereinstimmen, die Sie über den Delegaten aufrufen möchten.|Der erste Parameter der Delegatsignatur ist der Typ von `this` für das Objekt, das Sie aufrufen möchten.<br /><br /> Nach dem ersten Parameter muss die Delegatsignatur die Signatur der Funktion übereinstimmen, die Sie über den Delegaten aufrufen möchten.|  
|Instantiate|Wenn Sie einen gebundenen Delegaten instanziiert, können Sie einer Instanzfunktion angeben oder eine globale oder statische Memberfunktion.<br /><br /> Um eine Instanzfunktion anzugeben, ist der erste Parameter eine Instanz des Typs dessen Memberfunktion Sie aufrufen möchten und der zweite Parameter die Adresse der Funktion ist, die Sie aufrufen möchten.<br /><br /> Wenn Sie eine globale oder statische Memberfunktion aufrufen möchten, übergeben Sie einfach den Namen einer globalen Funktion oder Namen der statischen Memberfunktion.|Wenn Sie einem ungebundenen Delegaten instanziiert, übergeben Sie einfach die Adresse der Funktion, die Sie aufrufen möchten.|  
|Call|Wenn Sie einen gebundenen Delegaten aufrufen, übergeben Sie einfach die Parameter, die von der Delegatsignatur benötigt werden.|Wie ein gebundener Delegat, denken Sie nur daran, dass der erste Parameter eine Instanz des Objekts sein muss, das die Funktion enthält, die, die Sie aufrufen möchten.|  
  
 Dieses Beispiel demonstriert, wie Delegaten deklariert, ungebundene instanziiert und aufgerufen wird:  
  
```  
// unbound_delegates.cpp  
// compile with: /clr  
ref struct A {  
   A(){}  
   A(int i) : m_i(i) {}  
   void Print(int i) { System::Console::WriteLine(m_i + i);}  
  
private:  
   int m_i;  
};  
  
value struct V {  
   void Print() { System::Console::WriteLine(m_i);}  
   int m_i;  
};  
  
delegate void Delegate1(A^, int i);  
delegate void Delegate2(A%, int i);  
  
delegate void Delegate3(interior_ptr<V>);  
delegate void Delegate4(V%);  
  
delegate void Delegate5(int i);  
delegate void Delegate6();  
  
int main() {  
   A^ a1 = gcnew A(1);  
   A% a2 = *gcnew A(2);  
  
   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);  
   // delegate takes a handle  
   Unbound_Delegate1(a1, 1);  
   Unbound_Delegate1(%a2, 1);  
  
   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);  
   // delegate takes a tracking reference (must deference the handle)  
   Unbound_Delegate2(*a1, 1);  
   Unbound_Delegate2(a2, 1);  
  
   // instantiate a bound delegate to an instance member function  
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);  
   Bound_Del(1);  
  
   // instantiate value types  
   V v1 = {7};  
   V v2 = {8};  
  
   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);  
   Unbound_Delegate3(&v1);  
   Unbound_Delegate3(&v2);  
  
   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);  
   Unbound_Delegate4(v1);  
   Unbound_Delegate4(v2);  
  
   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);  
   Bound_Delegate3();  
}  
```  
  
 **Ausgabe**  
  
  **2**  
**3**  
**2**  
**3**  
**2**  
**7**  
**8**  
**7**  
**8**  
**7** Das folgende Beispiel zeigt, wie eine ungebundene Delegaten und die Schlüsselwörter [for each, in](../dotnet/for-each-in.md) verwendet, um Objekte in einer Auflistung durchlaufen und eine Memberfunktion auf jeder Instanz aufgerufen.  
  
```  
// unbound_delegates_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class RefClass {  
   String^ _Str;  
  
public:  
   RefClass( String^ str ) : _Str( str ) {}  
   void Print() { Console::Write( _Str ); }  
};  
  
delegate void PrintDelegate( RefClass^ );  
  
int main() {  
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );  
  
   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );  
  
   for ( int i = 0; i < a->Length; ++i )  
      a[i] = gcnew RefClass( i.ToString() );  
  
   for each ( RefClass^ R in a )  
      d( R );  
  
   Console::WriteLine();  
}  
```  
  
 Dieses Beispiel stellt einen Delegaten in den ungebundenen Accessorfunktionen einer Eigenschaft erstellt:  
  
```  
// unbound_delegates_3.cpp  
// compile with: /clr  
ref struct B {  
   property int P1 {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
  
private:  
   int m_i;  
};  
  
delegate void DelBSet(B^, int);  
delegate int DelBGet(B^);  
  
int main() {  
   B^ b = gcnew B;  
  
   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);  
   delBSet(b, 11);  
  
   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);     
   System::Console::WriteLine(delBGet(b));  
}  
```  
  
 **Ausgabe**  
  
  **11** Das folgende Beispiel zeigt, wie ein Multicastdelegaten aufruft, in dem eine Instanz gebunden ist und eine Instanz ungebunden ist.  
  
```  
// unbound_delegates_4.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int i) : m_i(i) {}  
  
   void f(R ^ r) {  
      System::Console::WriteLine("in f(R ^ r)");  
   }  
  
   void f() {  
      System::Console::WriteLine("in f()");  
   }  
  
private:  
   int m_i;  
};  
  
delegate void Del(R ^);  
  
int main() {  
   R ^r1 = gcnew R(11);  
   R ^r2 = gcnew R(12);  
  
   Del^ d = gcnew Del(r1, &R::f);  
   d += gcnew Del(&R::f);  
   d(r2);  
};  
```  
  
 **Ausgabe**  
  
  **f \(in R\-^ r\)**  
**in f\(\)** Das folgende Beispiel zeigt, wie Sie einem ungebundenen generischen Delegaten erstellt und aufgerufen wird.  
  
```  
// unbound_delegates_5.cpp  
// compile with: /clr  
ref struct R {  
   R(int i) : m_i(i) {}  
  
   int f(R ^) { return 999; }  
   int f() { return m_i + 5; }  
  
   int m_i;  
};  
  
value struct V {  
   int f(V%) { return 999; }  
   int f() { return m_i + 5; }   
  
   int m_i;  
};  
  
generic <typename T>  
delegate int Del(T t);  
  
generic <typename T>  
delegate int DelV(T% t);  
  
int main() {     
   R^ hr = gcnew R(7);  
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));  
  
   V v;  
   v.m_i = 9;  
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );  
}  
```  
  
 **Ausgabe**  
  
  **12**  
**14**   
## Siehe auch  
 [delegate](../windows/delegate-cpp-component-extensions.md)