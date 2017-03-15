---
title: "__restrict"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__restrict"
  - "__restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__restrict-Schlüsselwort [C++]"
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# __restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie der Modifizierer **\_\_declspec \( [restrict](../cpp/restrict.md) \)** gibt das `__restrict`\-Schlüsselwort an, dass ein Symbol im aktuellen Gültigkeitsbereich nicht mit einem Alias versehen ist.  Das Schlüsselwort `__restrict` unterscheidet sich vom `__declspec ( restrict )`\-Modifizierer folgendermaßen:  
  
-   Das Schlüsselwort `__restrict` ist nur auf Variablen gültig, und `__declspec ( restrict )` ist nur bei Funktionsdeklarationen und \-definitionen gültig.  
  
-   `__restrict` ähnelt `restrict` aus der Spezifikation C99, `__restrict` kann jedoch in C\+\+\- oder C\-Programmen verwendet werden.  
  
-   Wenn `__restrict` verwendet wird, gibt der Compiler die Kein\-Alias\-Eigenschaft einer Variablen nicht weiter.  Wenn Sie eine `__restrict`\-Variable einer Nicht\-`__restrict`\-Variablen zuweisen, ermöglicht der Compiler der Variable „non\-\_\_restrict“ weiterhin aliasiert zu werden.  Dies unterscheidet sich vom Verhalten des `restrict`\-Schlüsselworts der Spezifikation C99.  
  
 Wenn Sie das Verhalten einer vollständigen Funktion beeinflussen, ist es im Allgemeinen besser, `__declspec ( restrict )` anstatt das Schlüsselwort zu verwenden.  
  
 In Visual Studio 2015 und höher kann `__restrict` für C\+\+\-Verweise verwendet werden.  
  
> [!NOTE]
>  Bei Verwendung auf einer Variablen, die auch das [volatile](../cpp/volatile-cpp.md)\-Schlüsselwort aufweist, hat `volatile` Vorrang.  
  
## Beispiel  
  
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
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)