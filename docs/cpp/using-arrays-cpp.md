---
title: "Verwenden von Arrays (C++)"
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
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Arrays (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können auf einzelne Elemente eines Arrays zugreifen, indem Sie den Arrayfeldindex\-Operator \(`[ ]`\) verwenden.  Wenn ein eindimensionales Array in einem Ausdruck ohne Feldindex verwendet wird, wird der Arrayname als Zeiger auf das ersten Element im Array ausgewertet.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Wenn Sie mehrdimensionale Arrays verwenden, können Sie verschiedene Kombinationen in Ausdrücken verwenden.  
  
```  
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
  
 Im vorangegangenen Code ist `multi` ein dreidimensionales Array vom Typ `double`.  Der `p2multi`\-Zeiger zeigt auf ein Array vom Typ `double` der Größe drei.  In diesem Beispiel wird das Array mit einem, zwei oder drei Feldindizes verwendet.  Obwohl im Allgemeinen alle Feldindizes angegeben werden, wie in der `cout`\-Anweisung, ist es manchmal sinnvoll, eine bestimmte Teilmenge von Arrayelementen auszuwählen, wie in den Anweisungen gezeigt, die `cout` folgen.  
  
## Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)