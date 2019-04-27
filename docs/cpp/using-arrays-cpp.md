---
title: Verwenden von Arrays (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
ms.openlocfilehash: 7f7a987a2b4c18e59dd058ccfc4375c304188398
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152747"
---
# <a name="using-arrays-c"></a>Verwenden von Arrays (C++)

Sie können auf einzelne Elemente eines Arrays zugreifen, indem Sie den Arrayfeldindex-Operator (`[ ]`) verwenden. Wenn ein eindimensionales Array in einem Ausdruck ohne Feldindex verwendet wird, wird der Arrayname als Zeiger auf das ersten Element im Array ausgewertet.

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

Wenn Sie mehrdimensionale Arrays verwenden, können Sie verschiedene Kombinationen in Ausdrücken verwenden.

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

Im vorangehenden Code `multi` ein dreidimensionales Array vom Typ **doppelte**. Die `p2multi` Zeiger verweist auf ein Array vom Typ **doppelte** der Größe drei. In diesem Beispiel wird das Array mit einem, zwei oder drei Feldindizes verwendet. Obwohl im Allgemeinen alle Feldindizes angegeben werden, wie in der `cout`-Anweisung, ist es manchmal sinnvoll, eine bestimmte Teilmenge von Arrayelementen auszuwählen, wie in den Anweisungen gezeigt, die `cout` folgen.

## <a name="see-also"></a>Siehe auch

[Arrays](../cpp/arrays-cpp.md)