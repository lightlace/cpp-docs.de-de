---
title: "omp_unset_lock"
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
  - "omp_unset_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_lock OpenMP function"
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# omp_unset_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt eine Sperre.  
  
## Syntax  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) , der [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)initialisiert wurde, indem Besitz den Thread und das Ausführen der Funktion.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) als ein Beispiel für die Verwendung von `omp_unset_lock`.  
  
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)