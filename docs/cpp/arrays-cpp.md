---
title: Arrays (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b23727d7f6f5e8adcc220d57907a1d61f430bde3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-c"></a>Arrays (C++)
Ein Array ist eine Auflistung von gleichen Objekten. Der einfachste Fall eines Arrays ist ein Vektor, der mit der folgenden Sequenz deklariert werden kann:  
  
```  
  
      decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1. Der Deklarationsbezeichner:  
  
-   Ein optionaler Speicherklassenbezeichner.  
  
-   Optionale **const** und/oder `volatile` Spezifizierer.  
  
-   Der Typname der Elemente des Arrays.  
  
 2. Der Deklarator:  
  
-   Der Bezeichner.  
  
-   Ein Konstantenausdruck des ganzzahligen Typs, eingeschlossen in Klammern **[].** Wenn mehrere Dimensionen mit zusätzlichen Klammern deklariert wurden, kann der Konstante Ausdruck für den ersten Satz von Klammern weggelassen werden.  
  
-   Optionale zusätzliche Klammern, die Konstantenausdrücke einschließen.  
  
 3. Ein optionaler Initialisierer.  Finden Sie unter [Initialisierer](../cpp/initializers.md).  
  
 Die Anzahl von Elementen im Array wird durch den Konstantenausdruck angegeben. Das erste Element im Array ist 0. Element und das letzte Element ist das (*n*-1) Element, in dem  *n*  ist die Anzahl der Elemente, die das Array enthalten kann. Die *Konstantenausdruck* muss ein ganzzahliger Typ sein und muss größer als 0 sein. Ein Array der Größe 0 (null) ist gültig, nur, wenn das Array das letzte Feld in ist eine `struct` oder **Union** und wenn die Microsoft-Erweiterungen (/ Ze) aktiviert sind.  
  
 Die folgenden Beispiele zeigen, wie ein Array zur Laufzeit definiert wird:  
  
```  
// arrays.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main() {  
   using namespace std;  
   int size = 3, i = 0;  
  
   int* myarr = new int[size];  
  
   for (i = 0 ; i < size ; i++)  
      myarr[i] = 10;  
  
   for (i = 0 ; i < size ; i++)  
      printf_s("myarr[%d] = %d\n", i, myarr[i]);  
  
   delete [] myarr;  
}  
```  
  
 Arrays sind abgeleitete Typen und können daher von jedem anderen abgeleiteten oder grundlegenden Typ erstellt werden, außer von Funktionen, Verweisen und `void`.  
  
 Bei Arrays, die von anderen Arrays erstellt werden, handelt es sich um mehrdimensionale Arrays. Diese mehrdimensionalen Arrays werden angegeben, indem nacheinander mehrere Konstantenausdrücke in Klammern gesetzt werden. Ein Beispiel ist diese Deklaration:  
  
```  
int i2[5][7];  
```  
  
 Sie gibt ein Array vom Typ `int` an, das konzeptionell in einer zweidimensionalen Matrix von fünf Zeilen und sieben Spalten angeordnet ist, wie in der folgenden Abbildung gezeigt:  
  
 ![Konzeptionelles Layout eines mehrere &#45;-dimensionales Array](../cpp/media/vc38rc1.gif "vc38RC1")  
Konzeptionelles Layout eines mehrdimensionalen Arrays  
  
 In Deklarationen mehrdimensionaler Arrays mit einer Initialisiererliste (wie in beschrieben [Initialisierer](../cpp/initializers.md)), der Konstante Ausdruck, der angibt, das die Begrenzung für die erste Dimension kann ausgelassen werden. Zum Beispiel:  
  
```  
// arrays2.cpp  
// compile with: /c  
const int cMarkets = 4;  
// Declare a float that represents the transportation costs.  
double TransportCosts[][cMarkets] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }  
};  
```  
  
 Die vorhergehende Deklaration definiert ein Array, das aus vier Spalten mit je drei Zeilen besteht. Die Zeilen stellen Factorys dar und die Spalten Märkte, die von den Factorys beliefert werden. Die Werte entsprechen den Transportkosten von den Factorys zu den Märkten. Die erste Dimension des Arrays wird ausgelassen, aber der Compiler füllt sie aus, indem er den Initialisierer untersucht.  
  
 Themen in diesem Abschnitt:  
  
-   [Verwenden von Arrays](../cpp/using-arrays-cpp.md)  
  
-   [Arrays in Ausdrücken](../cpp/arrays-in-expressions.md)  
  
-   [Interpretation des Subscript-Operators](../cpp/interpretation-of-subscript-operator.md)  
  
-   [Dereferenzierung auf Arraytypen](../cpp/indirection-on-array-types.md)  
  
-   [Reihenfolge von C++-Arrays](../cpp/ordering-of-cpp-arrays.md)  
  
## <a name="example"></a>Beispiel  
 Die Möglichkeit des Umgehens von Begrenzungsspezifikationen für die erste Dimension eines mehrdimensionalen Arrays kann auch in Funktionsdeklarationen verwendet werden:  
  
```  
// multidimensional_arrays.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <limits>   // Includes DBL_MAX  
#include <iostream>  
  
const int cMkts = 4, cFacts = 2;  
  
// Declare a float that represents the transportation costs  
double TransportCosts[][cMkts] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }    
};  
  
// Calculate size of unspecified dimension  
const int cFactories = sizeof TransportCosts /  
                  sizeof( double[cMkts] );  
  
double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);  
  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   double MinCost;  
  
   if (argv[1] == 0) {  
      cout << "You must specify the number of markets." << endl;  
      exit(0);  
   }  
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);  
   cout << "The minimum cost to Market " << argv[1] << " is: "  
       << MinCost << "\n";  
}  
  
double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {  
   double MinCost = DBL_MAX;  
  
   for( int i = 0; i < cFacts; ++i )  
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?  
         MinCost : TransportCosts[i][Mkt];  
  
   return MinCost;  
}  
```  
  
```Output  
The minimum cost to Market 3 is: 17.29  
```  
  
## <a name="comments"></a>Kommentare  
 Die Funktion `FindMinToMkt` ist so geschrieben, dass das Hinzufügen von neuen Factorys keine Codeänderungen erfordert, sondern nur eine erneute Kompilierung.  
  
## <a name="see-also"></a>Siehe auch  
 