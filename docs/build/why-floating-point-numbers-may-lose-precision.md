---
title: Warum Gleitkommazahlen an Genauigkeit verlieren können
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 373ce9fa2c2c96fac349940076873a4a637a9dbe
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298713"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Warum Gleitkommazahlen an Genauigkeit verlieren können

Dezimalwerte für Gleit Komma Werte verfügen im Allgemeinen nicht über eine exakte binäre Darstellung. Dies ist eine neben Auswirkung darauf, wie die CPU Gleit Komma Daten darstellt. Aus diesem Grund kann es zu einem Genauigkeits Verlust kommen, und einige Gleit Komma Vorgänge können zu unerwarteten Ergebnissen führen.

Dieses Verhalten ist das Ergebnis einer der folgenden:

- Die binäre Darstellung der Dezimalzahl ist möglicherweise nicht exakt.

- Es gibt einen Typen Konflikt zwischen den verwendeten Zahlen (z. b. "float" und "Double").

Um das Verhalten zu beheben, stellen die meisten Programmierer entweder sicher, dass der Wert größer oder kleiner als das benötigte ist, oder Sie erhalten und verwenden eine binäre codierte Decimal (BCD)-Bibliothek, die die Genauigkeit beibehält.

Die binäre Darstellung von Gleit Komma Werten wirkt sich auf die Genauigkeit und Genauigkeit von Gleit Komma Berechnungen aus. Microsoft Visual C++ verwendet das [IEEE-Gleit Komma Format](ieee-floating-point-representation.md).

## <a name="example"></a>Beispiel

```c
// Floating-point_number_precision.c
// Compile options needed: none. Value of c is printed with a decimal
// point precision of 10 and 6 (printf rounded value by default) to
// show the difference
#include <stdio.h>

#define EPSILON 0.0001   // Define your own tolerance
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))

int main() {
   float a, b, c;

   a = 1.345f;
   b = 1.123f;
   c = a + b;
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result
   if (c == 2.468)            // Comment this line for correct result
      printf_s("They are equal.\n");
   else
      printf_s("They are not equal! The value of c is %13.10f "
                "or %f",c,c);
}
```

```Output
They are not equal! The value of c is  2.4679999352 or 2.468000
```

## <a name="comments"></a>Comments

Für Epsilon können Sie die Konstanten FLT_EPSILON verwenden, die für float als 1.192092896 e-07f definiert ist, oder DBL_EPSILON, das für Double AS 2.2204460492503131 e-016 definiert ist. Sie müssen float. h für diese Konstanten einschließen. Diese Konstanten werden als kleinste positive Zahl x definiert, sodass x + 1.0 nicht gleich 1,0 ist. Da es sich um eine sehr kleine Zahl handelt, sollten Sie benutzerdefinierte Toleranz für Berechnungen verwenden, die sehr große Zahlen umfassen.

## <a name="see-also"></a>Siehe auch

[Codeoptimierung](optimizing-your-code.md)
