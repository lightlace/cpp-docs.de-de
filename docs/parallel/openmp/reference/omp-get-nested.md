---
title: "omp_get_nested | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_nested OpenMP function"
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_get_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Wert zurück, der angibt, ob ein geschachtelter Parallelität aktiviert ist.  
  
## Syntax  
  
```  
int omp_get_nested( );  
```  
  
## Rückgabewert  
 Wenn ungleich 0 \(null\), geschachtelter Parallelität aktiviert ist.  
  
## Hinweise  
 Geschachtelter Parallelität wird mit [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) und [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)angegeben.  
  
 Weitere Informationen finden Sie unter [3.1.10 omp\_get\_nested Function](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) als ein Beispiel für die Verwendung von `omp_get_nested`.  
  
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)