---
title: "complex&lt;long double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::complex<long double>"
  - "complex<long double>"
  - "std.complex<long double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex<long double>-Funktion"
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# complex&lt;long double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das ein geordnetes Paar von Objekten speichert, die beide den Typ `long double` haben, wobei das erste Objekt dem reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil entspricht.  
  
## Syntax  
  
```  
template<>  
   class complex<long double> {  
public:  
   constexpr complex(  
      long double _RealVal = 0,   
      long double _ImagVal = 0  
   );  
complex(  
      constexpr complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Parameter  
 `_RealVal`  
 Der Wert des Typs **long double** für den reellen Teil der komplexen Zahl, die erstellt wird.  
  
 `_ImagVal`  
 Der Wert des Typs `long double` für den imaginären Teil der komplexen Zahl, die erstellt wird.  
  
 `_ComplexNum`  
 Die komplexe Zahl des Typs **double** oder **float**, deren reeller und imaginärer Teil dazu verwendet werden, eine zu erstellende komplexe Zahl des Typs `long double` zu initialisieren.  
  
## Rückgabewert  
 Eine komplexe Zahl des Typs `long double`.  
  
## Hinweise  
 Die explizite Spezialisierung der complex\-Vorlagenklasse in eine komplexe Klasse des Typs `long double` unterscheidet sich von der Vorlagenklasse nur in den Konstruktoren, die sie definiert.  Die Konvertierung von `long double` in **float** darf implizit erfolgen, aber die Konvertierung von **double** in `long double` muss **explizit** erfolgen.  Die Verwendung einer **expliziten** Konvertierung schließt die Initiierung mit Typkonvertierung über die Zuweisungssyntax aus.  
  
 Weitere Informationen zur Vorlagenklasse `complex` finden Sie unter [complex\-Klasse](../standard-library/complex-class.md).  Eine Liste der Mitglieder der Vorlagenklasse `complex` finden Sie unter  
  
## Beispiel  
  
```  
// complex_comp_ld.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <long double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 1.0 , 3.0 );  
   complex <long double> c2longdouble ( c2float );  
   cout << "Implicit conversion from type float to type long double,"  
        << "\n gives c2longdouble = " << c2longdouble << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type double  
   complex <double> c3double ( 3.0 , 4.0 );  
   complex <long double> c3longdouble ( c3double );  
   cout << "Implicit conversion from type long double to type float,"  
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
  
  **Specifying initial real & imaginary parts,**  
 **as type float gives c1 \= \(4,5\)**  
**Implicit conversion from type float to type long double,**  
 **gives c2longdouble \= \(1,3\)**  
**Implicit conversion from type long double to type float,**  
 **gives c3longdouble \= \(3,4\)**  
**The modulus of c3 is recovered from c3 using: abs \( c3 \) \= 5**  
**Argument of c3 is recovered from c3 using:**  
 **arg \( c3 \) \= 0.927295 radians, which is 53.1301 degrees.**   
## Anforderungen  
 **Header**: \<complex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [complex\-Klasse](../standard-library/complex-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)