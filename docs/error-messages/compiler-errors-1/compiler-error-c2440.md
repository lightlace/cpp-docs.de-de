---
title: Compilerfehler C2440 | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0789875fee672856dbc0eff429d2363a43963940
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2440"></a>Compilerfehler C2440
'Konvertierung': Konvertierung von 'Typ1' in 'Typ2' nicht möglich  
  
Der Compiler kann nicht aus umgewandelt `type1` auf `type2`.  
  
## <a name="example"></a>Beispiel  
C2440 kann verursacht werden, wenn Sie versuchen, ein nicht konstantes initialisieren `char*` (oder `wchar_t*`) mithilfe einen Zeichenfolgenliterals in C++-Code, wenn die compilerübereinstimmungsoption [/Zc: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) festgelegt ist. In C ist der Typ eines Zeichenfolgenliterals Array von `char`, aber in C++ ist der Array von `const char`. Dieses Beispiel generiert C2440:  
  
```cpp  
// C2440s.cpp  
// Build: cl /Zc:strictStrings /W3 C2440s.cpp  
// When built, the compiler emits:  
// error C2440: 'initializing' : cannot convert from 'const char [5]'   
// to 'char *'  
//        Conversion from string literal loses const qualifier (see  
// /Zc:strictStrings)  
  
int main() {  
   char* s1 = "test"; // C2440  
   const char* s2 = "tests"; // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch verursacht werden, wenn Sie versuchen, einen Zeiger auf ein Element in "void*" zu konvertieren. Im nächsten Beispiel wird C2440 generiert:  
  
```cpp  
// C2440.cpp  
class B {  
public:  
   void  f(){;}  
  
   typedef void (B::*pf)();  
  
   void f2(pf pf) {  
       (this->*pf)();  
       void* pp = (void*)pf;   // C2440  
   }  
  
   void f3() {  
      f2(f);  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch verursacht werden, wenn Sie versuchen, einen Typ umzuwandeln, der nur vorwärts deklariert jedoch nicht definiert ist. Dieses Beispiel generiert C2440:  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>Beispiel  
 Die C2440-Fehler in den Zeilen 15 und 16 des folgenden Beispielcodes sind durch die Meldung `Incompatible calling conventions for UDT return value` gekennzeichnet. Ein *UDT* ein benutzerdefinierten Typ, z. B. eine Klasse, Struktur oder Union ist. Derartige Inkompatibilitätsfehler treten auf, wenn die Aufrufkonvention eines UDTs, die im Rückgabetyp einer Vorwärtsdeklaration festgelegt wurde, Konflikte mit der aktuellen Aufrufkonvention des UDTs verursacht und zugleich ein Funktionszeiger betroffen ist.  
  
 Das Beispiel enthält zunächst Vorwärtsdeklarationen für eine Struktur und für eine Funktion, durch die die Struktur zurückgegeben wird. Der Compiler geht davon aus, dass die Struktur die C++-Aufrufkonvention verwendet. Darauf folgt die Strukturdefinition, die standardmäßig die C-Aufrufkonvention verwendet. Da der Compiler die Aufrufkonvention der Struktur nicht kennt, solange die Struktur nicht vollständig eingelesen ist, setzt er voraus, dass die Aufrufkonvention für die Struktur im Rückgabetyp von `get_c2` ebenfalls C++ entspricht.  
  
 Auf die Struktur folgt eine weitere Funktionsdeklaration, durch die die Struktur zurückgegeben wird. Zu diesem Zeitpunkt weiß der Compiler jedoch bereits, dass die Struktur die C++-Aufrufkonvention verwendet. Entsprechend wird der Funktionszeiger, durch den die Struktur zurückgegeben wird, erst nach der Strukturdefinition definiert. Daher ist dem Compiler bekannt, dass die Struktur die C++-Aufrufkonvention verwendet.  
  
 Um den durch inkompatible Aufrufkonventionen hervorgerufenen Fehler C2440 zu beheben, sollten Sie Funktionen deklarieren, die einen UDT nach der UDT-Definition zurückgeben.  
  
```cpp  
// C2440b.cpp  
struct MyStruct;  
  
MyStruct get_c1();  
  
struct MyStruct {  
   int i;  
   static MyStruct get_C2();  
};  
  
MyStruct get_C3();  
  
typedef MyStruct (*FC)();  
  
FC fc1 = &get_c1;   // C2440, line 15  
FC fc2 = &MyStruct::get_C2;   // C2440, line 16  
FC fc3 = &get_C3;  
  
class CMyClass {  
public:  
   explicit CMyClass( int iBar)  
      throw()   {  
   }  
  
   static CMyClass get_c2();  
};  
  
int main() {  
   CMyClass myclass = 2;   // C2440  
   // try one of the following  
   // CMyClass myclass{2};  
   // CMyClass myclass(2);  
  
   int *i;  
   float j;  
   j = (float)i;   // C2440, cannot cast from pointer to int to float  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch auftreten, wenn Sie einem inneren Zeiger 0 (null) zuweisen:  
  
```cpp  
// C2440c.cpp  
// compile with: /clr  
int main() {  
   array<int>^ arr = gcnew array<int>(100);  
   interior_ptr<int> ipi = &arr[0];  
   ipi = 0;   // C2440  
   ipi = nullptr;   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch bei nicht ordnungsgemäßer Verwendung einer benutzerdefinierten Konvertierung auftreten. Z. B. wenn ein Konvertierungsoperator definiert wurde als `explicit`, der Compiler kann nicht in eine implizite Konvertierung verwenden. Weitere Informationen zu benutzerdefinierten Konvertierungen finden Sie unter [benutzerdefinierten Konvertierungen (C + c++ / CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Dieses Beispiel generiert C2440:  
  
```cpp  
// C2440d.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   int i;  
   i = d;   // C2440  
   // Uncomment the following line to resolve.  
   // i = static_cast<int>(d);  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch auftreten, wenn Sie versuchen, eine Instanz eines Visual C++-Arrays erstellen, dessen Typ eine <xref:System.Array>.</xref:System.Array> ist  Weitere Informationen finden Sie unter [Arrays](../../windows/arrays-cpp-component-extensions.md).  Im nächsten Beispiel wird C2440 generiert:  
  
```cpp  
// C2440e.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440  
   // try the following line instead  
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2440 kann auch aufgrund von Änderungen in der Attributfunktion auftreten.  Im folgenden Beispiel wird C2440 generiert.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>Beispiel  
 Visual C++-Compiler nicht mehr ermöglicht die [Const_cast-Operator](../../cpp/const-cast-operator.md) unten beim Umwandeln-Quellcode an, die verwendet **"/ CLR"** Programmierung kompiliert wird.  
  
 Um den Fehler C2440 zu beheben, verwenden Sie den richtigen Umwandlungsoperator. Weitere Informationen finden Sie unter [Umwandlungsoperatoren](../../cpp/casting-operators.md).  
  
 Dieses Beispiel generiert C2440:  
  
```cpp  
// c2440g.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
int main() {  
   Derived ^d = gcnew Derived;  
   Base ^b = d;  
   d = const_cast<Derived^>(b);   // C2440  
   d = dynamic_cast<Derived^>(b);   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
C2440 kann aufgrund der Übereinstimmung Änderungen an den Compiler in Visual Studio 2015 Update 3 auftreten. Zuvor der Compiler nicht ordnungsgemäß behandelt bestimmte unterschiedlichen Ausdrücke als gleicher Typ identifizieren der Vorlage eine Übereinstimmung mit einem `static_cast` Vorgang. Nachdem der Compiler ordnungsgemäß Threadtypen und code basieren, die auf der vorherigen `static_cast` Verhalten ist unterbrochen. Um dieses Problem zu beheben, ändern Sie das Vorlagenargument aus, um den Typ des Vorlagenparameters übereinstimmt, oder verwenden Sie eine `reinterpret_cast` oder Umwandlung im C-Stil.
  
Dieses Beispiel generiert C2440:  
  
```cpp  
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3 
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.

```

## <a name="example"></a>Beispiel  
### <a name="copy-list-initialization"></a>copy-list-Initialisierung

Visual Studio 2017 und höher auslösen ordnungsgemäß Compiler-Fehler im Zusammenhang mit der Erstellung des Objekts mithilfe von Initialisiererlisten, die nicht in Visual Studio 2015 abgefangen wurden und zur abstürzen führen oder ein nicht definiertes Laufzeitverhalten. In C ++ 17-Liste-kopierinitialisierung der Compiler ist erforderlich, um einen expliziten Konstruktor für die überladungsauflösung zu berücksichtigen, jedoch muss einen Fehler wird ausgelöst, wenn Sie diese Überladung tatsächlich ausgewählt wird.

Im folgende Beispiel wird in Visual Studio 2015, aber nicht im Visual Studio-2017 kompiliert.

```cpp  
// C2440j.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot 
                         // convert from 'int' to 'const A &'
}
```  
  
Verwenden Sie direkte Initialisierung, um den Fehler zu korrigieren:  
  
```cpp  
// C2440k.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}  
```  

## <a name="example"></a>Beispiel
### <a name="cv-qualifiers-in-class-construction"></a>CV-Qualifizierer in der Klassenkonstruktion

In Visual Studio 2015 ignoriert der Compiler beim Generieren eines Klassenobjekts über einen Konstruktoraufruf manchmal fälschlicherweise die CV-Qualifizierer. Dies kann potenziell zu einem Absturz oder zu unerwartetem Laufzeitverhalten führen. Im folgende Beispiel in Visual Studio 2015 kompiliert wird, aber löst einen Compilerfehler in Visual Studio 2017 und höher:

```cpp
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Deklarieren Sie den Operator int() als konstant, um den Fehler zu korrigieren.

