---
title: "ordered (OpenMP Directives) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ordered"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered OpenMP directive"
ms.assetid: e1aa703e-d07d-4f6a-9b2a-f4f25203d850
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ordered (OpenMP Directives)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass Code mit einer parallelisierten Schleife z. B. für eine sequenzielle Schleife ausgeführt werden soll.  
  
## Syntax  
  
```  
#pragma omp ordered  
   structured-block  
```  
  
## Hinweise  
 Die **geordnet**\-Direktive muss innerhalb des dynamischen [for](../../../parallel/openmp/reference/for-openmp.md) eines Wertebereichs oder **für Ähnlichkeit** \- Konstrukt mit einer **geordnet**\-Klausel sein.  
  
 Die **geordnet**\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.6 ordered Construct](../../../parallel/openmp/2-6-6-ordered-construct.md).  
  
## Beispiel  
  
```  
// omp_ordered.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
static float a[1000], b[1000], c[1000];  
  
void test(int first, int last)   
{  
    #pragma omp for schedule(static) ordered  
    for (int i = first; i <= last; ++i) {  
        // Do something here.  
        if (i % 2)   
        {  
            #pragma omp ordered   
            printf_s("test() iteration %d\n", i);  
        }  
    }  
}  
  
void test2(int iter)   
{  
    #pragma omp ordered  
    printf_s("test2() iteration %d\n", iter);  
}  
  
int main( )   
{  
    int i;  
    #pragma omp parallel  
    {  
        test(1, 8);  
        #pragma omp for ordered  
        for (i = 0 ; i < 5 ; i++)  
            test2(i);  
    }  
}  
```  
  
  **Testen Sie die Iteration 1 \(\)**  
**Testen Sie die Iteration 3 \(\)**  
**Testen Sie die Iteration 5 \(\)**  
**Testen Sie die Iteration 7 \(\)**  
**test2 Iteration 0 \(\)**  
**test2 Iteration 1 \(\)**  
**test2 Iteration 2 \(\)**  
**test2 Iteration 3 \(\)**  
**test2 Iteration 4 \(\)**   
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)