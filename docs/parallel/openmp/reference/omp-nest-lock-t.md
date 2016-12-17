---
title: "omp_nest_lock_t"
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
  - "omp_nest_lock_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_nest_lock_t OpenMP data type"
ms.assetid: fceac9fb-96d2-42b0-af19-c9b078380618
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# omp_nest_lock_t
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein Typ, der eine Sperre für die folgenden Informationen enthält: ob die Sperre verfügbar, und die Identität des Threads, der die Anzahl der Schachtelungs und eine Sperre besitzt.  
  
 Die folgende Funktion verwenden **omp\_nest\_lock\_t**:  
  
-   [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)  
  
-   [omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)  
  
-   [omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)  
  
-   [omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)  
  
-   [omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)  
  
 Weitere Informationen finden Sie unter [3.2 Lock Functions](../../../parallel/openmp/3-2-lock-functions.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) als ein Beispiel für die Verwendung von **omp\_nest\_lock\_t**.  
  
## Siehe auch  
 [Data Types](../../../parallel/openmp/reference/openmp-data-types.md)