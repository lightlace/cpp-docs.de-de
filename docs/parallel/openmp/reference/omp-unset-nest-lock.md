---
title: "omp_unset_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_unset_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_nest_lock OpenMP function"
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# omp_unset_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt eine schachtelbare Sperre.  
  
## Syntax  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , der [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)initialisiert wurde, indem Besitz den Thread und das Ausführen der Funktion.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) als ein Beispiel für die Verwendung von `omp_unset_nest_lock`.  
  
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)