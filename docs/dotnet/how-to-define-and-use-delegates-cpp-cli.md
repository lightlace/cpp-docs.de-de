---
title: 'Vorgehensweise: definieren und Verwenden von Delegaten (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f400a03f1b9ae877ee7ec681cb038698a92598a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-use-delegates-ccli"></a>Gewusst wie: Definieren und Verwenden von Delegaten (C++/CLI)
In diesem Artikel wird gezeigt, wie zum Definieren und Verarbeiten von Delegaten in c++ / CLI.  
  
 Obwohl .NET Framework eine Anzahl von Delegaten enthält, können manchmal müssen Sie neue Delegaten definieren.  
  
 Das folgende Codebeispiel definiert einen Delegaten mit dem Namen `MyCallback`. Den Ereignisbehandlungscode – die Funktion, die aufgerufen wird, wenn diese neuen Delegaten ausgelöst wird – benötigen einen Rückgabetyp von `void` und ergreifen Sie eine <xref:System.String> Verweis.  
  
 Die main-Funktion verwendet eine statische Methode, die von definiert ist `SomeClass` zum Instanziieren der `MyCallback` delegieren. Der Delegat wird dann eine alternative Methode zum Aufrufen dieser Funktion, wie durch die Zeichenfolge "einfach" senden, um das Delegatobjekt veranschaulicht. Weiter, zusätzliche Instanzen von `MyCallback` miteinander verknüpft sind, und klicken Sie dann durch einen Aufruf des Delegaten-Objekts ausgeführt.  
  
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
  
```Output  
static SomeClass::Func - single  
static SomeClass::Func - chained  
static SomeClass::Func - chained  
OtherClass::Method - chained, num = 99  
OtherClass::Method - chained, num = 100  
```  
  
 Im nächste Codebeispiel wird gezeigt, wie ein Delegat mit einem Member einer Wertklasse zugeordnet.  
  
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
  
```Output  
test  
test  
```  
  
## <a name="how-to-compose-delegates"></a>Gewusst wie: Erstellen von Delegaten  
 Sie können die "`-`" Operator, um einen Delegaten für die Komponente aus einem zusammengesetzten Delegaten zu entfernen.  
  
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
  
```Output  
Invoking delegate a:  
Hello, A!  
Invoking delegate b:  
  Goodbye, B!  
Invoking delegate c:  
Hello, C!  
  Goodbye, C!  
Invoking delegate d:  
  Goodbye, D!  
```  
  
## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>Übergeben eines Delegaten ^ an eine native Funktion, die einen Funktionszeiger erwartet  
 In einer verwalteten Komponente können Sie eine systemeigene Funktion mit Zeigerparametern aufrufen, in denen kann die systemeigene Funktion klicken Sie dann die Member-Funktion, die verwaltete Komponente Delegaten aufrufen.  
  
 Dieses Beispiel erstellt die DLL-Datei, die von der systemeigenen Funktion exportiert:  
  
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
  
 Im nächste Beispiel nutzt die DLL-Datei und übergibt einen Delegaten-Handle an die systemeigene Funktion, die einen Funktionszeiger erwartet.  
  
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
  
```Output  
Call to Managed Function  
```  
  
## <a name="to-associate-delegates-with-unmanaged-functions"></a>Zuordnen von Delegaten zu nicht verwalteten Funktionen  
 Um einen Delegaten mit einer systemeigenen Funktion zuzuordnen, müssen Sie die systemeigene Funktion in einem verwalteten Typ umschließen und deklarieren Sie die Funktion über aufzurufende `PInvoke`.  
  
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
  
```Output  
hello  
```  
  
## <a name="to-use-unbound-delegates"></a>Verwenden Sie nicht gebundene Delegate  
 Sie können einen ungebundenen Delegaten verwenden, Übergabe eine Instanz des Typs, dessen Funktion aufgerufen wird, wenn der Delegat aufgerufen wird.  
  
 Nicht gebundene Delegate sind besonders nützlich, wenn die Objekte in einer Auflistung durchlaufen werden sollen – mit [für jedes in](../dotnet/for-each-in.md) Schlüsselwörter – eine Memberfunktion für jede Instanz aufgerufen.  
  
 Hier wird erklärt, wie Sie deklarieren, instanziieren und Aufrufen gebunden und ungebundenen Delegaten:  
  
|Aktion|Delegaten gebunden|Nicht gebundene Delegate|  
|------------|---------------------|-----------------------|  
|Declare|Die Signatur des Delegaten muss es sich um die Signatur der Funktion übereinstimmen, die durch Delegaten aufgerufen werden soll.|Der erste Parameter von der Signatur des Delegaten ist der Typ des `this` für das Objekt aufgerufen werden soll.<br /><br /> Nach den ersten Parameter muss die Signatur des Delegaten die Signatur der Funktion übereinstimmen, die Sie über den Delegaten aufrufen möchten.|  
|Instanziieren|Wenn Sie einen gebundenen Delegaten instanziieren, können Sie eine Instanzfunktion oder eine globale oder statische Memberfunktion angeben.<br /><br /> Um eine Instanzfunktion anzugeben, der erste Parameter ist eine Instanz des Typs, dessen Memberfunktion aufgerufen werden soll, und der zweite Parameter ist die Adresse der Funktion, die Sie aufrufen möchten.<br /><br /> Wenn Sie eine globale oder statische Memberfunktion aufrufen möchten, übergeben Sie einfach den Namen einer globalen Funktion oder der Name der statischen Memberfunktion.|Wenn Sie einen ungebundenen Delegaten instanziieren, übergeben Sie einfach die Adresse der Funktion, die Sie aufrufen möchten.|  
|Call|Wenn Sie einen gebundenen Delegaten aufrufen, übergeben Sie einfach die Parameter, die von der Signatur des Delegaten erforderlich sind.|Identisch mit einer Grenze delegieren, aber beachten Sie, dass der erste Parameter eine Instanz des Objekts sein muss, die die Funktion enthält, die Sie aufrufen möchten.|  
  
 Dieses Beispiel veranschaulicht die deklarieren, instanziieren und ungebundene Delegaten aufrufen:  
  
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
  
```Output  
2  
3  
2  
3  
2  
7  
8  
7  
8  
7  
```  
  
 Das nächste Beispiel veranschaulicht die Verwendung von ungebundenen Delegaten und der [für jedes in](../dotnet/for-each-in.md) Schlüsselwörtern, um Objekte in einer Auflistung durchlaufen und eine Memberfunktion für jede Instanz aufrufen.  
  
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
  
 Dieses Beispiel erstellt einen ungebundenen Delegaten an eine Eigenschaft Accessor-Funktionen:  
  
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
  
```Output  
11  
```  
  
 Im folgende Beispiel wird gezeigt, wie ein multicast-Delegat aufgerufen wird, in dem eine Instanz gebunden ist und eine Instanz entfernt wird.  
  
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
  
```Output  
in f(R ^ r)  
in f()  
```  
  
 Im nächste Beispiel veranschaulicht das Erstellen und einen ungebundenen generischen Delegaten aufrufen.  
  
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
  
```Output  
12  
14  
```  
  
## <a name="see-also"></a>Siehe auch  
 [delegate (Komponentenerweiterungen für C++)](../windows/delegate-cpp-component-extensions.md)