---
title: "Arrays (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++]"
  - "Deklarieren von Arrays, Informationen über das Deklarieren von Arrays"
  - "Mehrdimensionale Arrays"
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Array ist eine Auflistung von gleichen Objekten.  Der einfachste Fall eines Arrays ist ein Vektor, der mit der folgenden Sequenz deklariert werden kann:  
  
```  
  
      decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1.  Der Deklarationsbezeichner:  
  
-   Ein optionaler Speicherklassenbezeichner.  
  
-   Optionale **const**\- und\/oder `volatile`\-Bezeichner.  
  
-   Der Typname der Elemente des Arrays.  
  
 2.  Der Deklarator:  
  
-   Der Bezeichner.  
  
-   Ein Konstantenausdruck des ganzzahligen Typs, eingeschlossen in Klammern, **\[\].** Wenn mehrere Dimensionen mit zusätzlichen Klammern deklariert wurden, kann der Konstantenausdruck im ersten Satz von Klammern weggelassen werden.  
  
-   Optionale zusätzliche Klammern, die Konstantenausdrücke einschließen.  
  
 3.  Ein optionaler Initialisierer.  Weitere Informationen erhalten Sie unter [Initialisierer](../cpp/initializers.md).  
  
 Die Anzahl von Elementen im Array wird durch den Konstantenausdruck angegeben.  Das erste Element im Array ist das nullte Element, und das letzte Element ist das Element \(*n*\-1\), wobei *n* die Zahl der Elemente angibt, die das Array enthalten kann.  Der *Konstantenausdruck* muss ein ganzzahliger Typ und größer als 0 sein.  Ein Array der Größe null ist nur gültig, wenn das Array das letzte Feld in `struct` oder **union** ist, und die Verwendung der Microsoft\-Erweiterungen \(\/Ze\) aktiviert ist.  
  
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
  
 Bei Arrays, die von anderen Arrays erstellt werden, handelt es sich um mehrdimensionale Arrays.  Diese mehrdimensionalen Arrays werden angegeben, indem nacheinander mehrere Konstantenausdrücke in Klammern gesetzt werden.  Ein Beispiel ist diese Deklaration:  
  
```  
int i2[5][7];  
```  
  
 Sie gibt ein Array vom Typ `int` an, das konzeptionell in einer zweidimensionalen Matrix von fünf Zeilen und sieben Spalten angeordnet ist, wie in der folgenden Abbildung gezeigt:  
  
 ![Konzeptionelles Layout eines mehrdimensionalen Arrays](../cpp/media/vc38rc1.png "vc38RC1")  
Konzeptionelles Layout eines mehrdimensionalen Arrays  
  
 In den Deklarationen mehrdimensionaler Arrays mit einer Initialisiererliste \(wie unter [Initialisierer](../cpp/initializers.md) beschrieben\), kann der Konstantenausdruck weggelassen werden, der die Begrenzungen für die erste Dimension angibt.  Beispiel:  
  
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
  
 Die vorhergehende Deklaration definiert ein Array, das aus vier Spalten mit je drei Zeilen besteht.  Die Zeilen stellen Factorys dar und die Spalten Märkte, die von den Factorys beliefert werden.  Die Werte entsprechen den Transportkosten von den Factorys zu den Märkten.  Die erste Dimension des Arrays wird ausgelassen, aber der Compiler füllt sie aus, indem er den Initialisierer untersucht.  
  
 Themen in diesem Abschnitt:  
  
-   [Verwenden von Arrays](../cpp/using-arrays-cpp.md)  
  
-   [Arrays in Ausdrücken](../cpp/arrays-in-expressions.md)  
  
-   [Interpretation des Subscript\-Operators](../cpp/interpretation-of-subscript-operator.md)  
  
-   [Dereferenzierung auf Arraytypen](../cpp/indirection-on-array-types.md)  
  
-   [Reihenfolge von C\+\+\-Arrays](../cpp/ordering-of-cpp-arrays.md)  
  
## Beispiel  
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
  
  **Der Mindestaufwand für Markt 3 ist: 17,29**   
## Kommentare  
 Die Funktion `FindMinToMkt` ist so geschrieben, dass das Hinzufügen von neuen Factorys keine Codeänderungen erfordert, sondern nur eine erneute Kompilierung.  
  
## Siehe auch  
 [C\+\+ Abstract Declarators](assetId:///e7e18c18-0cad-4450-942b-d27e1d4dd088)