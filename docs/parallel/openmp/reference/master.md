---
title: "master"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "master"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "master OpenMP directive"
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# master
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass nur das Vorlagen\-threadshould einen Abschnitt des Programms ausführen.  
  
## Syntax  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## Hinweise  
 Die **Master**\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Die [single](../../../parallel/openmp/reference/single.md)\-Direktive können Sie nicht angeben, dass ein Abschnitt des Codes auf einem einzigen Thread Masterthread, der ausgeführt werden soll.  
  
 Weitere Informationen finden Sie unter [2.6.1 master Construct](../../../parallel/openmp/2-6-1-master-construct.md).  
  
## Beispiel  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
  **a \[0\] \= 0**  
**a \[1\] \= 1**  
**a \[2\] \= 4**  
**a \[3\] \= 9**  
**a \[4\] \= 16**   
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)