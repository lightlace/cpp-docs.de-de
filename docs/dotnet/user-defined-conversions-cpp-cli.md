---
title: Benutzerdefinierte Konvertierungen (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3515b9da7513080e825457d98aa06bccb63a1029
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="user-defined-conversions-ccli"></a>Benutzerdefinierte Konvertierungen (C++/CLI)
Dieser Abschnitt beschreibt die benutzerdefinierten Konvertierungen (UDP), wenn einer der Typen in der Konvertierung ein Verweis oder eine Instanz von einem Werttyp oder Verweistyp ist.  
  
## <a name="implicit-and-explicit-conversions"></a>Implizite und explizite Konvertierungen  
 Eine benutzerdefinierte Konvertierung kann entweder implizit oder explizit sein.  Eine UDC muss implizit, wenn die Konvertierung nicht zu einem Verlust von Informationen führt. Andernfalls sollte eine explizite UDC definiert werden.  
  
 Eine systemeigene Klasse Konstruktor kann verwendet werden, auf einen Verweis- oder Werttyp-Typ in eine systemeigene Klasse konvertieren.  
  
 Weitere Informationen zu Konvertierungen finden Sie unter [Boxing](../windows/boxing-cpp-component-extensions.md) und [Standardkonvertierungen](../cpp/standard-conversions.md).  
  
```  
// mcpp_User_Defined_Conversions.cpp  
// compile with: /clr  
#include "stdio.h"  
ref class R;  
class N;  
  
value class V {  
   static operator V(R^) {  
      return V();  
   }  
};  
  
ref class R {  
public:  
   static operator N(R^);  
   static operator V(R^) {  
      System::Console::WriteLine("in R::operator N");  
      return V();  
   }  
};  
  
class N {  
public:  
   N(R^) {  
      printf("in N::N\n");  
   }  
};  
  
R::operator N(R^) {  
   System::Console::WriteLine("in R::operator N");  
   return N(nullptr);  
}  
  
int main() {  
   // Direct initialization:  
   R ^r2;  
   N n2(r2);   // direct initialization, calls constructor  
   static_cast<N>(r2);   // also direct initialization  
  
   R ^r3;  
   // ambiguous V::operator V(R^) and R::operator V(R^)  
   // static_cast<V>(r3);     
}  
```  
  
 **Ausgabe**  
  
```Output  
in N::N  
in N::N  
```  
  
## <a name="convert-from-operators"></a>Convert-From-Operatoren  
 Convert-from-Operatoren erstellen Sie ein Objekt der Klasse in der der Operator definiert ist aus einem Objekt eines beliebigen anderen Klasse.  
  
 C++-Standard unterstützt nicht die Convert-from-Operatoren. Standard C++ werden Konstruktoren für diesen Zweck verwendet. Allerdings bei Verwendung von CLR-Typen, unterstützen Visual C++ syntaktische Convert-from-Operatoren aufrufen.  
  
 Um auch mit anderen CLS-kompatiblen Sprachen zusammenarbeiten, möchten Sie möglicherweise jeder unäre benutzerdefinierten Konstruktor für eine bestimmte Klasse mit einem entsprechenden Convert-from-Operator zu umschließen.  
  
 Convert-from-Operatoren:  
  
-   Wird als statische Funktionen definiert werden.  
  
-   Optionen sind möglich (für Konvertierungen, die keine wie Short-Int-Genauigkeit verloren gehen) implizit oder explizit, wenn ein Genauigkeitsverlust möglicherweise.  
  
-   Ein Objekt der enthaltenden Klasse muss zurückgegeben werden.  
  
-   Hat den Typ "von" als einzigen Parameter-Typ.  
  
 Das folgende Beispiel zeigt eine implizite und explizite "Convert-from", der eine benutzerdefinierte (UDP)-Konvertierungsoperator.  
  
```  
// clr_udc_convert_from.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
  
   MyDouble(int i) {  
      d = static_cast<double>(i);  
      System::Console::WriteLine("in constructor");  
   }  
  
   // Wrap the constructor with a convert-from operator.  
   // implicit UDC because conversion cannot lose precision  
   static operator MyDouble (int i) {  
      System::Console::WriteLine("in operator");  
      // call the constructor  
      MyDouble d(i);  
      return d;  
   }  
  
   // an explicit user-defined conversion operator  
   static explicit operator signed short int (MyDouble) {  
      return 1;  
   }  
};  
  
int main() {  
   int i = 10;  
   MyDouble md = i;  
   System::Console::WriteLine(md.d);  
  
   // using explicit user-defined conversion operator requires a cast    
   unsigned short int j = static_cast<unsigned short int>(md);  
   System::Console::WriteLine(j);  
}  
```  
  
 **Ausgabe**  
  
```Output  
in operator  
in constructor  
10  
1  
```  
  
## <a name="convert-to-operators"></a>Convert-to-Operatoren  
 Convert-to-Operatoren konvertieren Sie ein Objekt der Klasse in der der Operator, zu einem anderen Objekt definiert ist. Das folgende Beispiel zeigt eine implizite, Convert-to, benutzerdefinierte Konvertierungsoperator:  
  
```  
// clr_udc_convert_to.cpp  
// compile with: /clr  
using namespace System;  
value struct MyInt {  
   Int32 i;  
  
   // convert MyInt to String^  
   static operator String^ ( MyInt val ) {  
      return val.i.ToString();  
   }  
  
   MyInt(int _i) : i(_i) {}  
};  
  
int main() {  
   MyInt mi(10);  
   String ^s = mi;  
   Console::WriteLine(s);  
}  
```  
  
 **Ausgabe**  
  
```Output  
10  
```  
  
 Ein Konvertierungsoperator explizite benutzerdefinierte Convert-to-eignet sich für Konvertierungen, die Daten auf irgendeine Weise verlieren. Um eine explizite Convert-Operators aufrufen zu können, muss eine Umwandlung verwendet werden.  
  
```  
// clr_udc_convert_to_2.cpp  
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
   d.d = 10.3;  
   System::Console::WriteLine(d.d);  
   int i = 0;  
   i = static_cast<int>(d);  
   System::Console::WriteLine(i);  
}  
```  
  
 **Ausgabe**  
  
```Output  
10.3  
10  
```  
  
## <a name="to-convert-generic-classes"></a>Generische Klassen konvertieren  
 Sie können eine generische Klasse in t konvertieren.  
  
```  
// clr_udc_generics.cpp  
// compile with: /clr  
generic<class T>   
public value struct V {  
   T mem;  
   static operator T(V v) {  
      return v.mem;  
   }  
  
   void f(T t) {  
      mem = t;  
   }  
};  
  
int main() {  
   V<int> v;  
   v.f(42);  
   int i = v;  
   i += v;  
   System::Console::WriteLine(i == (42 * 2) );  
}  
```  
  
 **Ausgabe**  
  
```Output  
True  
```  
  
 Einen konvertierungskonstruktor akzeptiert einen Typ und verwendet, um ein Objekt zu erstellen.  Einen konvertierungskonstruktor mit nur direkte Initialisierung aufgerufen wird. Umwandlungen werden keine Konvertierung von Konstruktoren aufgerufen werden. Standardmäßig sind die Konvertierung von Konstruktoren explizite für CLR-Typen.  
  
```  
// clr_udc_converting_constructors.cpp  
// compile with: /clr  
public ref struct R {  
   int m;  
   char c;  
  
   R(int i) : m(i) { }  
   R(char j) : c(j) { }  
};  
  
public value struct V {  
   R^ ptr;  
   int m;  
  
   V(R^ r) : ptr(r) { }  
   V(int i) : m(i) { }  
};  
  
int main() {   
   R^ r = gcnew R(5);  
  
   System::Console::WriteLine( V(5).m);  
   System::Console::WriteLine( V(r).ptr);  
}  
```  
  
 **Ausgabe**  
  
```Output  
5  
R  
```  
  
 In diesem Codebeispiel wird eine implizite statische Konvertierungsfunktion eines expliziten konvertierungskonstruktors identisch.  
  
```  
public value struct V {  
   int m;  
   V(int i) : m(i) {}  
   static operator V(int i) {  
      V v(i*100);  
      return v;  
   }  
};  
  
public ref struct R {  
   int m;  
   R(int i) : m(i) {}  
   static operator R^(int i) {  
      return gcnew R(i*100);  
   }  
};  
  
int main() {  
   V v(13);   // explicit  
   R^ r = gcnew R(12);   // explicit  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
  
   // explicit ctor can't be called here: not ambiguous  
   v = 5;  
   r = 20;  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
}  
```  
  
 **Ausgabe**  
  
```Output  
13  
12  
500  
2000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)