---
title: "omp_test_lock"
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
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Versucht, eine Sperre festzulegen, blockiert aber nicht Thread ausgeführt werden.  
  
## Syntax  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) , der [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)initialisiert wurde.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## Beispiel  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **simple\_lock abgerufenes \- Thread 1**  
**Shared Thread 1 \- simple\_lock**  
**Fehler beim Abrufen simple\_lock \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**Fehler beim Abrufen simple\_lock \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**simple\_lock abgerufenes \- Thread 2**  
**Fehler beim Abrufen simple\_lock \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**Fehler beim Abrufen simple\_lock \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**Shared Thread 2 \- simple\_lock**  
**Fehler beim Abrufen simple\_lock \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**simple\_lock abgerufenes \- Thread 0**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**Shared Thread 0 \- simple\_lock**  
**Fehler beim Abrufen simple\_lock \- Thread 3**  
**simple\_lock abgerufenes \- Thread 3**  
**Shared Thread 3 \- simple\_lock**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)