---
title: "parallel"
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
  - "parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel OpenMP directive"
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Definiert einen parallelen Bereich mit dem Code, der von mehreren Threads parallel ausgeführt werden.  
  
## Syntax  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `clause` \(optional\)  
 Null oder mehr Klauseln.  Weitere Informationen finden Sie im Abschnitt " Hinweise " für eine Liste von Klauseln, die von **Ähnlichkeit**unterstützt werden.  
  
## Hinweise  
 Die **Ähnlichkeit** unterstützen die folgenden Direktiven OpenMP\-Klauseln:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num\_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Ähnlichkeit** kann mit den [sections](../../../parallel/openmp/reference/sections-openmp.md) und [for](../../../parallel/openmp/reference/for-openmp.md)\-Direktive verwendet werden.  
  
 Weitere Informationen finden Sie unter [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die Anzahl der Threads festgelegt und einen parallelen Bereich definiert.  Standardmäßig ist die Anzahl von Threads gleich der Anzahl von logischen Prozessoren auf dem Computer.  Wenn Sie beispielsweise einen Computer mit einem physischen Prozessoren verfügen, der die Hyperthreading aktiviert hat, verfügt es zwei logische Prozessoren und daher zwei Threads.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
  **Hallo der Thread 0**  
**Hallo der Thread 1**  
**Hallo der Thread 2**  
**Hallo der Thread 3**   
## Kommentar  
 Beachten Sie, dass die Reihenfolge der Ausgabe auf verschiedenen Computern unterschiedlich sein kann.  
  
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)