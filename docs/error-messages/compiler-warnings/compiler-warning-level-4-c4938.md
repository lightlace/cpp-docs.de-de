---
title: "Compilerwarnung (Stufe 4) C4938"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4938"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4938"
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4938
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": Die reduction\-Gleitkommavariable kann zu inkonsistenten Ergebnissen bei \/fp:strict oder \#pragma fenv\_access führen.  
  
 [\/fp:strict](../../build/reference/fp-specify-floating-point-behavior.md) oder [fenv\_access](../../preprocessor/fenv-access.md) sollte nicht mit reduction\-Gleitkommavorgängen von OpenMP verwendet werden, da die Summe in einer anderen Reihenfolge berechnet wird. Daher können die Ergebnisse von den Ergebnissen ohne "\/openmp" abweichen.  
  
 Im folgenden Beispiel wird C4938 generiert:  
  
```  
// C4938.cpp // compile with: /openmp /W4 /fp:strict /c // #pragma fenv_access(on) extern double *a; double test(int first, int last) { double sum = 0.0; #pragma omp parallel for reduction(+: sum)   // C4938 for (int i = first ; i <= last ; ++i) sum += a[i]; return sum; }  
```  
  
 Ohne explizite Parallelisierung wird die Summe wie folgt berechnet:  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 Mit expliziter Parallelisierung \(und zwei Threads\) wird die Summe wie folgt berechnet:  
  
```  
sum1 = a[first] + ... a[first + last / 2]; sum2 = a[(first + last / 2) + 1] + ... a[last]; sum = sum1 + sum2;  
```