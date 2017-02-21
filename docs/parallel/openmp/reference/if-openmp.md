---
title: "if (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "if OpenMP clause"
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# if (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob eine Schleife in der Serie oder parallel ausgeführt werden sollte.  
  
## Syntax  
  
```  
if(expression)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `expression`  
 Ein ganzzahliger Ausdruck, der ausgewertet wird, wenn er true \(\), Ungleich 0 \(null\) wird der Code im parallelen Bereich wird parallel auszuführen.  Wenn der Ausdruck false \(null\) ergibt, wird der parallelen Bereichs in der Serie ausgeführt \(durch einen einzelnen Thread.\)  
  
## Hinweise  
 `if` gilt für die folgenden Direktiven an:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Beispiel  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
  **0 \= val serialisiert**  
**val \= 2, parallelisiert mit 2 Threads**   
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)