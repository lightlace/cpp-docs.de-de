---
title: "Compilerfehler C2440"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2440"
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierung': Konvertierung von 'Typ1' in 'Typ2' nicht möglich  
  
 Der Compiler ist nicht in der Lage, '`type1`' in '`type2`' umzuwandeln.  
  
## Beispiel  
 C2440 kann verursacht werden, wenn Sie versuchen, ein nicht konstantes `char*` \(oder `wchar_t*`\) mithilfe eines Zeichenfolgenliterals in C\+\+\-Code zu initialisieren, wenn die Compilerübereinstimmungsoption [\/Zc:strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) festgelegt ist.  In C ist der Typ eines Zeichenfolgenliterals ein Array von `char`, aber in C\+\+ ist es ein Array von `const` `char`.  Dieses Beispiel generiert C2440:  
  
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
  
## Beispiel  
 C2440 kann auch verursacht werden, wenn Sie versuchen, einen Zeiger auf ein Element in "void\*" zu konvertieren.  Im nächsten Beispiel wird C2440 generiert:  
  
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
  
## Beispiel  
 C2440 kann auch verursacht werden, wenn Sie versuchen, einen Typ umzuwandeln, der nur vorwärts deklariert jedoch nicht definiert ist.  Dieses Beispiel generiert C2440:  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## Beispiel  
 Die C2440\-Fehler in den Zeilen 15 und 16 des folgenden Beispielcodes sind durch die Meldung `Incompatible calling conventions for UDT return value` gekennzeichnet. \(Ein UDT \(user\-defined type\) ist ein benutzerdefinierter Typ, z. B. eine Klasse, Struktur oder Union.\) Derartige Inkompatibilitätsfehler treten auf, wenn die Aufrufkonvention eines UDTs, die im Rückgabetyp einer Vorwärtsdeklaration festgelegt wurde, Konflikte mit der aktuellen Aufrufkonvention des UDTs verursacht und zugleich ein Funktionszeiger betroffen ist.  
  
 Das Beispiel enthält zunächst Vorwärtsdeklarationen für eine Struktur und für eine Funktion, durch die die Struktur zurückgegeben wird. Der Compiler geht davon aus, dass die Struktur die C\+\+\-Aufrufkonvention verwendet.  Darauf folgt die Strukturdefinition, die standardmäßig die C\-Aufrufkonvention verwendet.  Da der Compiler die Aufrufkonvention der Struktur nicht kennt, solange die Struktur nicht vollständig eingelesen ist, setzt er voraus, dass die Aufrufkonvention für die Struktur im Rückgabetyp von `get_c2` ebenfalls C\+\+ entspricht.  
  
 Auf die Struktur folgt eine weitere Funktionsdeklaration, durch die die Struktur zurückgegeben wird. Zu diesem Zeitpunkt weiß der Compiler jedoch bereits, dass die Struktur die C\+\+\-Aufrufkonvention verwendet.  Entsprechend wird der Funktionszeiger, durch den die Struktur zurückgegeben wird, erst nach der Strukturdefinition definiert. Daher ist dem Compiler bekannt, dass die Struktur die C\+\+\-Aufrufkonvention verwendet.  
  
 Um den durch inkompatible Aufrufkonventionen hervorgerufenen Fehler C2440 zu beheben, sollten Sie Funktionen deklarieren, die einen UDT nach der UDT\-Definition zurückgeben.  
  
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
  
## Beispiel  
 C2440 kann auch auftreten, wenn Sie einem inneren Zeiger 0 \(null\) zuweisen:  
  
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
  
## Beispiel  
 C2440 kann auch bei nicht ordnungsgemäßer Verwendung einer benutzerdefinierten Konvertierung auftreten.  Weitere Informationen über benutzerdefinierte Konvertierungen finden Sie unter [Benutzerdefinierte Konvertierungen](../../dotnet/user-defined-conversions-cpp-cli.md)\).  Dieses Beispiel generiert C2440:  
  
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
  
## Beispiel  
 C2440 kann auch bei dem Versuch auftreten, eine Instanz eines Visual C\+\+\-Arrays vom Typ <xref:System.Array> zu erstellen.  Weitere Informationen finden Sie unter [Arrays](../../windows/arrays-cpp-component-extensions.md).  Im nächsten Beispiel wird C2440 generiert:  
  
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
  
## Beispiel  
 C2440 kann auch aufgrund von Änderungen im Attributfeature auftreten.  Im folgenden Beispiel wird C2440 generiert.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## Beispiel  
 Der Visual C\+\+\-Compiler lässt die Verwendung von [const\_cast\-Operator](../../cpp/const-cast-operator.md) zur Abwärtsumwandlung beim Kompilieren von Quellcode mit der **\/clr**\-Programmierung nicht mehr zu.  
  
 Um den Fehler C2440 zu beheben, verwenden Sie den richtigen Umwandlungsoperator.  Weitere Informationen finden Sie unter [Umwandlungsoperatoren](../../cpp/casting-operators.md).  
  
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
  
## Beispiel  
 C2440 kann auch durch **\/clr:oldSyntax** erzeugt werden:  
  
```cpp  
// c2440h.cpp  
// compile with: /clr:oldSyntax  
__gc class Base {};  
__gc class Derived : public Base {};  
int main() {  
   Derived *d = new Derived;  
   Base *b = d;  
   d = const_cast<Derived*>(b);   // C2440  
   d = dynamic_cast<Derived*>(b);   // OK  
}  
```