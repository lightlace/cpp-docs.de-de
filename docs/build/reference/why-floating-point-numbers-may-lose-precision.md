---
title: Warum Gleitkommazahlen an Genauigkeit verlieren können | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb673f087d98f6c7acdd1e98b5649cc84a48d277
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376136"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Warum Gleitkommazahlen an Genauigkeit verlieren können
Dezimale Gleitkommawerte müssen die genaue binäre Darstellung in der Regel nicht. Dies ist ein Nebeneffekt der wie die CPU Gleitkommadaten darstellt. Aus diesem Grund kann Genauigkeitsverlust auftreten, und einige Gleitkommaoperationen können zu unerwarteten Ergebnissen führen.  
  
 Dieses Verhalten ist das Ergebnis eines der folgenden:  
  
-   Die binäre Darstellung der Dezimalzahl möglicherweise nicht genau.  
  
-   Es liegt ein Typenkonflikt zwischen den verwendeten Zahlen (z. B. mischen "float" und Double).  
  
 Um das Problem zu beheben, können Sie die meisten Programmierer entweder sicher, dass der Wert größer ist oder kleiner als erforderlich ist, oder sie erhalten und verwenden eine Binary Coded Decimal (BCD)-Bibliothek, die die Genauigkeit beibehält.  
  
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
 Für EPSILON können Sie die FLT_EPSILON, der für "float" als 1.192092896e definiert ist – 07F, oder die DBL_EPSILON-Konstante, die für Double als 2.2204460492503131e definiert wird-016. Sie müssen float.h für diese Konstanten enthalten. Diese Konstanten sind definiert als die kleinste positive Zahl x, z. B. X + 1,0 ist nicht gleich 1.0. Da dies eine sehr kleine Zahl ist, sollten Sie benutzerdefinierte Toleranz für Berechnungen im Zusammenhang mit sehr großen Zahlen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)