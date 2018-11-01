---
title: Initialisieren von Arrays
ms.date: 11/04/2016
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
ms.openlocfilehash: e055e7759865fc151176097c6f0afd9ee237f4c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447085"
---
# <a name="initializing-arrays"></a>Initialisieren von Arrays

Wenn eine Klasse über einen Konstruktor verfügt, werden Arrays dieser Klasse von einem Konstruktor initialisiert. Wenn weniger Elemente in der Initialisiererliste als Elemente im Array vorhanden sind, wird der Standardkonstruktor für die verbleibenden Elemente verwendet. Wenn kein Standardkonstruktor für die Klasse definiert wird, muss die Initialisiererliste abgeschlossen sein, d. h. es muss ein Initialisierer für jedes Element im Array vorhanden sein.

Betrachten Sie die `Point`-Klasse, die zwei Konstruktoren definiert:

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

Das erste Element von `aPoint` wird unter Verwendung des Konstruktors `Point( int, int )` erstellt; die verbleibenden zwei Elemente werden unter Verwendung des Standardkonstruktors erstellt.

Statische Memberarrays (ob **const** oder nicht) kann in ihren Definitionen (außerhalb der Klassendeklaration) initialisiert werden. Zum Beispiel:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```