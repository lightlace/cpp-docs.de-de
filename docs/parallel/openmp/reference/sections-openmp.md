---
title: "sections (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section"
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sections OpenMP directive"
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# sections (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Identifiziert die von allen Threads aufgeteilt werden soll, Codeabschnitten.  
  
## Syntax  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `clause` \(optional\)  
 Null oder mehr Klauseln.  Weitere Informationen finden Sie im Abschnitt " Hinweise " für eine Liste von Klauseln, die von **Abschnitte**unterstützt werden.  
  
## Hinweise  
 Die **Abschnitte**\-Direktive kann keine oder mehrere **Abschnitt**\-Direktive enthalten.  
  
 Die **Abschnitte** unterstützen die folgenden Direktiven OpenMP\-Klauseln:  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 Wenn **Ähnlichkeit** ebenfalls angegeben wird, kann `clause` jede Klausel sein, die von der **Ähnlichkeit** oder **Abschnitte**\-Direktive außer `nowait`akzeptiert wird.  
  
 Weitere Informationen finden Sie unter [2.4.2 sections Construct](../../../parallel/openmp/2-4-2-sections-construct.md).  
  
## Beispiel  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
  **Hallo der Thread 0**  
**Hallo der Thread 0**   
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)