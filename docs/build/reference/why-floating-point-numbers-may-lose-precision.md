---
title: Warum Gleitkommazahlen an Genauigkeit verlieren können
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 6e6f758e7a683a28189123b03252223476ac732a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442665"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Warum Gleitkommazahlen an Genauigkeit verlieren können

Dezimale Gleitkommawerte müssen in der Regel nicht genaue binäre Darstellung. Dies ist ein Nebeneffekt der Darstellungsweise von der CPU Gleitkommadaten. Aus diesem Grund treten unter Umständen Präzisionsverlust, und einige Operationen mit Gleitkommazahlen können zu unerwarteten Ergebnissen führen.

Dieses Verhalten ist das Ergebnis eines der folgenden:

- Die binäre Darstellung der Dezimalzahl möglicherweise nicht genau.

- Es ist ein Typenkonflikt zwischen den verwendeten Zahlen (z. B. Mischen von "float" und Double).

Um das Problem zu beheben, können Sie die meisten Programmierer, die Stellen Sie sicher, dass der Wert größer ist oder kleiner als erforderlich ist, oder sie erhalten und verwenden eine Binary Coded Decimal (BCD)-Bibliothek, die die Genauigkeit gewährleistet wird.

Binäre Darstellung von Gleitkommawerten wirkt sich auf die Genauigkeit und die Genauigkeit von gleitkommaberechnungen. Microsoft Visual C++ verwendet [IEEE-Gleitkomma-Format](../../build/reference/ieee-floating-point-representation.md).

## <a name="example"></a>Beispiel

```
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

## <a name="comments"></a>Kommentare

Für EPSILON können Sie die FLT_EPSILON, die für "float" als 1.192092896e definiert wird – 07F, oder DBL_EPSILON-Konstante, die für den Double-Wert als 2.2204460492503131e definiert wird-016. Sie müssen float.h für diese Konstanten enthalten. Diese Konstanten sind definiert als die kleinste positive Zahl x, z. B. X + 1,0 ist nicht gleich 1.0. Da dies eine verhältnismäßig kleine Anzahl ist, sollten Sie die benutzerdefinierte Toleranz für Berechnungen mit sehr großen Mengen verwenden.

## <a name="see-also"></a>Siehe auch

[Codeoptimierung](../../build/reference/optimizing-your-code.md)