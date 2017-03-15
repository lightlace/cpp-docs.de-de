---
title: "num_threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_threads OpenMP clause"
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Legt die Anzahl von Threads in einem Team Thread fest.  
  
## Syntax  
  
```  
num_threads(num)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `num`  
 Die Anzahl von Threads  
  
## Hinweise  
 Die `num_threads`\-Klausel verfügt über die gleichen Funktionen wie die [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)\-Funktion.  
  
 `num_threads` gilt für die folgenden Direktiven an:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [parallel](../../../parallel/openmp/reference/parallel.md) als ein Beispiel für die Verwendung von `num_threads`\-Klausel.  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)