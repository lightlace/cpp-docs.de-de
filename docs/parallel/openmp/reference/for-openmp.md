---
title: "for (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "for"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for OpenMP directive"
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# for (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Bewirkt, dass die Arbeit, die in eine for\-Schleife innerhalb eines parallelen Bereichs unter Threads aufgeteilt werden sollen.  
  
## Syntax  
  
```  
#pragma omp [parallel] for [clauses]  
   for_statement  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `clause` \(optional\)  
 Null oder mehr Klauseln.  Weitere Informationen finden Sie im Abschnitt " Hinweise " für eine Liste von Klauseln, die von **nach**unterstützt werden.  
  
 `for_statement`  
 A for\-Schleife.  Nicht definiertes Verhalten tritt auf, wenn Benutzercode in for\-Schleife die Indexvariable ändert.  
  
## Hinweise  
 Die **nach** unterstützen die folgenden Direktiven OpenMP\-Klauseln:  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [geordnet](../../../parallel/openmp/reference/ordered-openmp-directives.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [Verringerung](../../../parallel/openmp/reference/reduction.md)  
  
-   [Zeitplan](../../../parallel/openmp/reference/schedule.md)  
  
 Wenn **Ähnlichkeit** ebenfalls angegeben wird, kann `clause` jede Klausel sein, die von der **Ähnlichkeit** oder **nach**\-Direktive außer **nowait**akzeptiert wird.  
  
 Weitere Informationen finden Sie unter [2.4.1 für Konstrukt](../../../parallel/openmp/2-4-1-for-construct.md).  
  
## Beispiel  
  
```  
// omp_for.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <math.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define NUM_START 1  
#define NUM_END 10  
  
int main() {  
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;  
   int nThreads = 0, nTmp = nStart + nEnd;  
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *   
                               unsigned(abs(nTmp))) / 2;  
   int nSumCalc = uTmp;  
  
   if (nTmp < 0)  
      nSumCalc = -nSumCalc;  
  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)  
   {  
      #pragma omp master  
      nThreads = omp_get_num_threads();  
  
      #pragma omp for  
      for (i=nStart; i<=nEnd; ++i) {  
            #pragma omp atomic  
            nSum += i;  
      }  
   }  
  
   if  (nThreads == NUM_THREADS) {  
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);  
      nRet = 0;  
   }  
   else {  
      printf_s("Expected %d OpenMP threads, but %d were used.\n",  
               NUM_THREADS, nThreads);  
      nRet = 1;  
   }  
  
   if (nSum != nSumCalc) {  
      printf_s("The sum of %d through %d should be %d, "  
               "but %d was reported!\n",  
               NUM_START, NUM_END, nSumCalc, nSum);  
      nRet = 1;  
   }  
   else  
      printf_s("The sum of %d through %d is %d\n",  
               NUM_START, NUM_END, nSum);  
}  
```  
  
  **4 OpenMP\-Threads verwendet wurden.  Die Summe von 1 bis 10 ist 55.**    
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)