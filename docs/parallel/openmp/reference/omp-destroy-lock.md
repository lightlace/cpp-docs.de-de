---
title: "omp_destroy_lock"
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
  - "omp_destroy_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_destroy_lock OpenMP function"
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# omp_destroy_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Deinitialisiert eine Sperre.  
  
## Syntax  
  
```  
void omp_destroy_lock(  
   omp_lock_t *lock  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) , der [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)initialisiert wurde.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.2 omp\_destroy\_lock and omp\_destroy\_nest\_lock Functions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) als ein Beispiel für die Verwendung von `omp_destroy_lock`.  
  
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)