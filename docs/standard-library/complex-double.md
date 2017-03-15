---
title: "complex&lt;double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.complex<double>"
  - "complex<double>"
  - "std::complex<double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "komplexe < Double >-Funktion"
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# complex&lt;double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ **double** haben*,* wobei das erste Objekt dem reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil entspricht.  
  
## Syntax  
  
```  
template<>  
   class complex<double> {  
public:  
   constexpr complex(  
      double _RealVal = 0,   
      double _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr explicit complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Parameter  
 `_RealVal`  
 Der Wert vom Typ **double** für den reellen Teil der zu erstellenden komplexen Zahl.  
  
 `_ImagVal`  
 Der Wert vom Typ **double** für den imaginären Teil der zu erstellenden komplexen Zahl.  
  
 `_ComplexNum`  
 Die komplexe Zahl vom Typ **float** oder `long double`, deren reeller und imaginärer Teil zum Initialisieren einer zu erstellenden komplexen Zahl vom Typ **double** verwendet werden.  
  
## Rückgabewert  
 Eine komplexe Zahl vom Typ **double**.  
  
## Hinweise  
 Die explizite Spezialisierung der complex\-Vorlagenklasse in eine komplexe Klasse des Typs **double** unterscheidet sich von der Vorlagenklasse nur in den Konstruktoren, die sie definiert. Die Konvertierung von **float** in **double** darf implizit erfolgen, aber die Konvertierung von `long double` in **double** muss **explizit** erfolgen. Die Verwendung einer **expliziten** Konvertierung schließt die Initiierung mit Typkonvertierung über die Zuweisungssyntax aus.  
  
 Weitere Informationen zu der Vorlagenklasse `complex`, finden Sie unter [complex\-Klasse](../standard-library/complex-class.md). Eine Liste der Member der `complex`\-Vorlagenklasse finden Sie unter .  
  
## Beispiel  
  
```  
// complex_comp_dbl.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type double gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 4.0 , 5.0 );  
   complex <double> c2double ( c2float );  
   cout << "Implicit conversion from type float to type double,"  
        << "\n gives c2double = " << c2double << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 4.0 , 5.0 );  
   complex <double> c3double ( c3longdouble );  
   cout << "Explicit conversion from type float to type double,"  
        << "\n gives c3longdouble = " << c3longdouble << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3longdouble );  
   double argc3 = arg ( c3longdouble );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
 **Angabe ersten realen und imaginären Teile als Typ double bietet c1 \= \(4,5\) implizite Konvertierung vom Typ Float, double, bietet c2double eingeben \(4,5\) explizite Konvertierung vom Typ Float, double, bietet c3longdouble Eingabe \= \= \(4,5\) der Modulo von c3 mit c3 wiederhergestellt wird: abs \(c3\) \= 6.40312 Argument von c3 mit c3 wiederhergestellt wird: Arg \(c3\) \= 0.896055 Bogenmaß 51.3402 Grad ist.**   
## Anforderungen  
 **Header**: \<complex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [complex\-Klasse](../standard-library/complex-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)