---
title: "Benutzerdefinierte Konvertierungen (C++/CLI)"
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
  - "Benutzerdefinierte Konvertierungen [C++]"
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerdefinierte Konvertierungen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Abschnitt erläutert benutzerdefinierte Konvertierungen \(UDC\), wenn einer der Typen in der Konvertierung ein Verweis oder eine Instanz eines Werttyps oder des Verweistyps ist.  
  
## Implizite und explizite Konvertierungen  
 Benutzerdefinierte Konvertierung kann entweder implizit oder explizit sein.  Ein UDC sollte implizit sein, wenn die Konvertierung kein Informationsverlust führt.  Andernfalls sollte ein expliziter UDC definiert werden.  
  
 Konstruktor kann einer der systemeigene Klasse verwendet werden, um einen Verweis oder einen Werttyp zu einer systemeigenen Klasse zu konvertieren.  
  
 Weitere Informationen über Konvertierungen, finden Sie unter [Boxing](../windows/boxing-cpp-component-extensions.md) und [Standardkonvertierungen](../cpp/standard-conversions.md).  
  
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
  
  **in N::N**  
**in N::N**   
## Convert\-From\-Operatoren  
 Convert\-from\-Operatoren erstellen ein Objekt der Klasse, in der der Operator von einem Objekt einer anderen Klasse definiert wird.  
  
 Standard\-C\+\+ unterstützt nicht convert\-from\-Operatoren; Standard\-C\+\+\-Verwendungskonstruktoren zu diesem Zweck.  Wenn, CLR verwenden, gibt, Visual C\+\+ bietet syntaktische Unterstützung zum Aufrufen von convert\-from\-Operatoren ein.  
  
 Um sich mit anderen CLS\-kompatiblen Sprachen einbeziehen, können Sie jeden benutzerdefinierten unären Konstruktor für eine angegebene Klasse mit einem entsprechenden convert\-from\-Operator umschließen.  
  
 Convert\-from\-Operatoren:  
  
-   Wird als statische Funktionen definiert.  
  
-   Kann entweder implizit \(für Konvertierungen, die Genauigkeit nicht wie Kurz\-zuint verlieren\) oder explizit sein, wenn es einen Genauigkeitsverlust gibt.  
  
-   Gibt ein Objekt der enthaltenden Klasse zurück.  
  
-   Hat "von" Typ1 als einziger Parametertyp.  
  
 Im folgenden Beispiel wird implizites und explizites "convert\-from", benutzerdefinierten Konvertierungs \(udc\)\- Operator an.  
  
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
  
  **im Operator**  
**im Konstruktor**  
**10**  
**1**   
## CONVERT\-zu den Operatoren  
 CONVERT\-zuden Operatoren konvertieren Sie ein Objekt der Klasse, in der der Operator zu einem anderen Objekt definiert wird.  Das folgende Beispiel zeigt ein implizites, CONVERT\-zu, benutzerdefinierter Konvertierungsoperator an:  
  
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
  
  **10** Ein explizites benutzerdefiniertes CONVERT\-zum Konvertierungsoperators ist für Konvertierungen geeignet, die ggf. Daten auf eine bestimmte Weise verlieren.  Um ein explizites CONVERT\-zum Operator aufzurufen, muss eine Umwandlung verwendet werden.  
  
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
  
  **10.3**  
**10**   
## So konvertieren generische Klassen  
 Sie können eine generische Klasse zu konvertieren. T  
  
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
  
  **True** Ein konvertierender Konstruktor akzeptiert einen Typ und verwendet diesen, um ein Objekt zu erstellen.  Ein konvertierender Konstruktor wird nur mit direkten Initialisierung bezeichnet; Typumwandlungen rufen nicht das Konvertieren von Konstruktoren auf.  Standardmäßig Konvertieren sind Konstruktoren für CLR\-Typen explizit.  
  
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
  
  **5**  
**R** In diesem Codebeispiel führt eine implizite statische Konvertierungsfunktion die gleiche Aufgabe wie ein Konstruktor der expliziten Konvertierung.  
  
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
  
  **13**  
**12**  
**500**  
**2000**   
## Siehe auch  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)