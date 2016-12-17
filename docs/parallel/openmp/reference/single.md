---
title: "single"
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
  - "Single"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single OpenMP directive"
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# single
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Hiermit können Sie nicht angeben, dass ein Abschnitt des Codes auf einem einzigen Thread Masterthread, der ausgeführt werden soll.  
  
## Syntax  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### Parameter  
 `clause` \(optional\)  
 Null oder mehr Klauseln.  Weitere Informationen finden Sie im Abschnitt " Hinweise " für eine Liste von Klauseln, die von **Einfach**unterstützt werden.  
  
## Hinweise  
 Die **Einfach** unterstützen die folgenden Direktiven OpenMP\-Klauseln:  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 Die [master](../../../parallel/openmp/reference/master.md)\-Direktive können Sie angeben, dass ein Codeabschnitt nur auf dem Masterthread ausgeführt werden soll.  
  
 Weitere Informationen finden Sie unter [2.4.3 single Construct](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## Beispiel  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
  **Lesen von Eingaben**  
**Berechnet Suchergebnisse**  
**Berechnet Suchergebnisse**  
**Schreiben von Ausgabe**   
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)