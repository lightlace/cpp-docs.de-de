---
title: __restrict | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __restrict_cpp
dev_langs: C++
helpviewer_keywords: __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2c21872c5d6fe6000038a3a2f4fe39451b566dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="restrict"></a>__restrict
Wie die **__declspec ( [beschränken](../cpp/restrict.md) )** Modifizierer, der `__restrict` -Schlüsselwort Gibt an, dass ein Symbol, das keinen Alias im aktuellen Bereich besitzt. Das Schlüsselwort `__restrict` unterscheidet sich vom `__declspec ( restrict )`-Modifizierer folgendermaßen:  
  
-   Das Schlüsselwort `__restrict` ist nur auf Variablen gültig, und `__declspec ( restrict )` ist nur bei Funktionsdeklarationen und -definitionen gültig.  
  
-   `__restrict` ähnelt `restrict` aus der Spezifikation C99, `__restrict` kann jedoch in C++- oder C-Programmen verwendet werden.  
  
-   Wenn `__restrict` verwendet wird, gibt der Compiler die Kein-Alias-Eigenschaft einer Variablen nicht weiter. Wenn Sie eine `__restrict`-Variable einer Nicht-`__restrict`-Variablen zuweisen, ermöglicht der Compiler der Variable „non-__restrict“ weiterhin aliasiert zu werden. Dies unterscheidet sich vom Verhalten des `restrict`-Schlüsselworts der Spezifikation C99.  
  
 Wenn Sie das Verhalten einer vollständigen Funktion beeinflussen, ist es im Allgemeinen besser, `__declspec ( restrict )` anstatt das Schlüsselwort zu verwenden.  
  
 In Visual Studio 2015 und höher kann `__restrict` für C++-Verweise verwendet werden.  
  
> [!NOTE]
>  Wenn für eine Variable verwendet wird, das ebenfalls den [volatile](../cpp/volatile-cpp.md) Schlüsselwort `volatile` Vorrang.  
  
## <a name="example"></a>Beispiel  
  
```  
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)