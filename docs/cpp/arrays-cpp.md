---
title: Arrays (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: 746a6b5a2122a7ccdd207d278d285af3e448d7ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550669"
---
# <a name="arrays-c"></a>Arrays (C++)

Ein Array ist eine Auflistung von gleichen Objekten. Der einfachste Fall eines Arrays ist ein Vektor, der mit der folgenden Sequenz deklariert werden kann:

> *Decl-Specifiers* *Bezeichner* **\[** *Konstantenausdruck* **]**<br/>
> *Decl-Specifiers* *Bezeichner*  **\[]**<br/>
> *Decl-Specifiers* *Bezeichner* **\[]\[** *Konstantenausdruck* **]** . sein. sein.<br/>
> *Decl-Specifiers* *Bezeichner* **\[** *Konstantenausdruck* **]** **\[** *Konstantenausdruck* **]** . sein. sein.

1. Der Deklarationsbezeichner:

   - Ein optionaler Speicherklassenbezeichner.

   - Optionale **const** und/oder **flüchtige** Spezifizierer.

   - Der Typname der Elemente des Arrays.

1. Der Deklarator:

   - Der Bezeichner.

   - Ein Konstantenausdruck des ganzzahligen Typs, eingeschlossen in Klammern  **\[]**. Wenn mehrere Dimensionen mit zusätzlichen Klammern deklariert wurden, kann der Konstantenausdruck im ersten Satz von Klammern weggelassen werden.

   - Optionale zusätzliche Klammern, die Konstantenausdrücke einschließen.

1. Ein optionaler Initialisierer. Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md).

Die Anzahl der Elemente im Array erhält von der *Konstantenausdruck*. Das erste Element im Array ist 0. das-Element, und das letzte Element ist das (*n*-1) Element, in denen *n* ist die Anzahl der Elemente, die das Array enthalten kann. Die *Konstantenausdruck* muss ein ganzzahliger Typ sein und muss größer als 0 sein. Ein Array der Größe 0 (null) ist zulässig, nur, wenn das Array das letzte Feld ist ein **Struktur** oder **Union** und wenn die Microsoft-Erweiterungen (/ Ze) aktiviert sind.

Die folgenden Beispiele zeigen, wie ein Array zur Laufzeit definiert wird:

```cpp
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

Arrays sind abgeleitete Typen und von anderen abgeleiteten oder grundlegenden Typen mit Ausnahme von Funktionen, verweisen daher konstruiert werden kann und **"void"**.

Bei Arrays, die von anderen Arrays erstellt werden, handelt es sich um mehrdimensionale Arrays. Diese mehrdimensionalen Arrays werden angegeben, indem nacheinander mehrere Konstantenausdrücke in Klammern gesetzt werden. Ein Beispiel ist diese Deklaration:

```cpp
int i2[5][7];
```

Es gibt ein Array vom Typ **Int**, konzeptionell in einer zweidimensionalen Matrix von fünf Zeilen und sieben Spalten angeordnet, wie in der folgenden Abbildung gezeigt:

![Konzeptionelles Layout eines mehreren&#45;-dimensionales Array](../cpp/media/vc38rc1.gif "vc38RC1") konzeptionelles Layout eines mehrdimensionalen Arrays

In Deklarationen mehrdimensionaler Arrays mit einer Initialisiererliste (wie in beschrieben [Initialisierer](../cpp/initializers.md)), kann der Konstantenausdruck, der angibt, die Grenzen für die erste Dimension ausgelassen werden. Zum Beispiel:

```cpp
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

- [Verwenden von Arrays](../cpp/using-arrays-cpp.md)

- [Arrays in Ausdrücken](../cpp/arrays-in-expressions.md)

- [Interpretation des Subscript-Operators](../cpp/interpretation-of-subscript-operator.md)

- [Dereferenzierung auf Arraytypen](../cpp/indirection-on-array-types.md)

- [Reihenfolge von C++-Arrays](../cpp/ordering-of-cpp-arrays.md)

## <a name="example"></a>Beispiel

Die Möglichkeit des Umgehens von Begrenzungsspezifikationen für die erste Dimension eines mehrdimensionalen Arrays kann auch in Funktionsdeklarationen verwendet werden:

```cpp
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
