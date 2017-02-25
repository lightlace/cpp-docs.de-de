---
title: "Warum Gleitkommazahlen an Genauigkeit verlieren k&#246;nnen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DBL_EPSILON-Konstante"
  - "Gleitkommazahlen, Präzision"
  - "FLT_EPSILON-Konstante"
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Warum Gleitkommazahlen an Genauigkeit verlieren k&#246;nnen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dezimale Gleitkommawerte können im Allgemeinen binär nicht exakt dargestellt werden.  Das ist ein Nebeneffekt der Darstellungsweise von Gleitkommazahlen durch die CPU.  Aus diesem Grund könnte ein gewisser Genauigkeitsverlust auftreten, und manche Gleitkommaoperationen können unerwartete Ergebnisse hervorbringen.  
  
 Dieses Verhalten kann auf die folgenden Umstände zurückgeführt werden:  
  
-   Die Binärdarstellung der Dezimalzahl ist möglicherweise nicht genau.  
  
-   Es gibt einen Typenkonflikt zwischen den verwendeten Zahlen \(z. B., wenn **float** und **double** gemischt werden\).  
  
 Um das Verhalten zu korrigieren, stellen die meisten Programmierer entweder sicher, dass der Wert größer oder kleiner als benötigt ist, oder sie verwenden eine BCD \(Binary Coded Decimal\)\-Bibliothek, durch die Genauigkeit gewährleistet wird.  
  
 Die binäre Darstellung von Gleitkommawerten beeinflusst die Genauigkeit und Exaktheit von Gleitkommaberechnungen.  Microsoft Visual C\+\+ verwendet das [IEEE\-Gleitkommaformat](../../build/reference/ieee-floating-point-representation.md).  
  
## Beispiel  
  
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
  
  **Sie sind nicht gleich\!  Der Wert für c ist 2,4679999352 oder 2,468000**    
## Kommentare  
 Für EPSILON können Sie die FLT\_EPSILON\-Konstante verwenden, die für float mit 1.192092896e\-07F definiert ist, oder die DBL\_EPSILON\-Konstante, die für double mit 2.2204460492503131e\-016 definiert ist.  Sie müssen float.h für diese Konstanten einschließen.  Die Konstanten werden als die kleinste positive Zahl x definiert, bei der x\+1,0 nicht gleich 1,0 ist.  Da dies eine sehr kleine Zahl ist, ist es ratsam, eine benutzerdefinierte Toleranz für Berechnungen mit sehr großen Zahlen anzuwenden.  
  
## Siehe auch  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)