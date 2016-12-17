---
title: "omp_init_lock"
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
  - "omp_init_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_init_lock OpenMP function"
ms.assetid: 7a65e3e2-2e31-4645-964c-c1e82e2a4d0e
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# omp_init_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine einfache Zuweisung.  
  
## Syntax  
  
```  
void omp_init_lock(  
   omp_lock_t *lock  
);  
```  
  
#### Parameter  
 `lock`  
 Eine Variable vom Typ [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md).  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.2.1 omp\_init\_lock and omp\_init\_nest\_lock Functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).  
  
## Beispiel  
  
```  
// omp_init_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t my_lock;  
  
int main() {  
   omp_init_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num( );  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_lock(&my_lock);  
         printf_s("Thread %d - starting locked region\n", tid);  
         printf_s("Thread %d - ending locked region\n", tid);  
         omp_unset_lock(&my_lock);  
      }  
   }  
  
   omp_destroy_lock(&my_lock);  
}  
```  
  
  **Bereich gesperrten \- Thread 0 starten**  
**Thread 0 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 0 starten**  
**Thread 0 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 0 starten**  
**Thread 0 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 0 starten**  
**Thread 0 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 0 starten**  
**Thread 0 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 1 starten**  
**Thread 1 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 1 starten**  
**Thread 1 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 1 starten**  
**Thread 1 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 1 starten**  
**Thread 1 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 1 starten**  
**Thread 1 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 2 starten**  
**Thread 2 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 2 starten**  
**Thread 2 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 2 starten**  
**Thread 2 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 2 starten**  
**Thread 2 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 2 starten**  
**Thread 2 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 3 starten**  
**Thread 3 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 3 starten**  
**Thread 3 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 3 starten**  
**Thread 3 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 3 starten**  
**Thread 3 \- verschlossener Bereich des Endes**  
**Bereich gesperrten \- Thread 3 starten**  
**Thread 3 \- verschlossener Bereich des Endes**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)