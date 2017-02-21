---
title: "omp_test_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_test_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_nest_lock OpenMP function"
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_test_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Versucht, eine Sperre festzulegen schachtelbare Ausführung der Thread blockiert aber nicht.  
  
## Syntax  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , der [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)initialisiert wurde.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## Beispiel  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
  **nestable\_lock abgerufenes \- Thread 1**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**Thread erneut nestable\_lock abgerufenes \- 1**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**Shared Thread 1 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**Shared Thread 1 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**nestable\_lock abgerufenes \- Thread 3**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**Thread erneut nestable\_lock abgerufenes \- 3**  
**Fehler beim Abrufen nestable\_lock \- Thread 0**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Shared Thread 3 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Shared Thread 3 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**nestable\_lock abgerufenes \- Thread 0**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Thread erneut nestable\_lock abgerufenes \- 0**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Shared Thread 0 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**Shared Thread 0 \- nestable\_lock**  
**Fehler beim Abrufen nestable\_lock \- Thread 2**  
**nestable\_lock abgerufenes \- Thread 2**  
**Thread erneut nestable\_lock abgerufenes \- 2**  
**Shared Thread 2 \- nestable\_lock**  
**Shared Thread 2 \- nestable\_lock**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)