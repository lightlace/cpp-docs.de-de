---
title: Verwenden von Arrays (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7cab4f8bcc4deb8353f4cef0828af829da008e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-arrays-c"></a>Verwenden von Arrays (C++)
Sie können auf einzelne Elemente eines Arrays zugreifen, indem Sie den Arrayfeldindex-Operator (`[ ]`) verwenden. Wenn ein eindimensionales Array in einem Ausdruck ohne Feldindex verwendet wird, wird der Arrayname als Zeiger auf das ersten Element im Array ausgewertet.  
  
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
  
 Im vorangegangenen Code ist `multi` ein dreidimensionales Array vom Typ `double`. Der `p2multi`-Zeiger zeigt auf ein Array vom Typ `double` der Größe drei. In diesem Beispiel wird das Array mit einem, zwei oder drei Feldindizes verwendet. Obwohl im Allgemeinen alle Feldindizes angegeben werden, wie in der `cout`-Anweisung, ist es manchmal sinnvoll, eine bestimmte Teilmenge von Arrayelementen auszuwählen, wie in den Anweisungen gezeigt, die `cout` folgen.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)