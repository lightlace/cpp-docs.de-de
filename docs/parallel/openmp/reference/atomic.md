---
title: "atomic"
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
  - "atomic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atomic OpenMP directive"
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# atomic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass eine Speicheradresse an, die atomar aktualisiert wird.  
  
## Syntax  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### Parameter  
 `expression`  
 Die Anweisung, durch die das lvalue enthält, dessen Speicheradresse, die Sie mit mehreren schützen möchten, schreibt.  Weitere Informationen über Formen des juristischen Fachausdrucks finden Sie in der OpenMP\-Spezifikation.  
  
## Hinweise  
 Die `atomic`\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.4 atomic Construct](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## Beispiel  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
  **Anzahl von Threads: 10**   
## Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)