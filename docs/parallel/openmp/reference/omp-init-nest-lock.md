---
title: "omp_init_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_init_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_init_nest_lock OpenMP function"
ms.assetid: cf749ec5-de78-4186-9588-ac7c42b02463
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_init_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine Sperre.  
  
## Syntax  
  
```  
void omp_init_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `lock`  
 Eine Variable vom Typ [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md).  
  
## Hinweise  
 Die anfängliche Anzahl Schachtelungs ist Null.  
  
 Weitere Informationen finden Sie unter [3.2.1 omp\_init\_lock and omp\_init\_nest\_lock Functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).  
  
## Beispiel  
  
```  
// omp_init_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t my_lock;  
  
void Test() {  
   int tid = omp_get_thread_num( );  
   omp_set_nest_lock(&my_lock);  
   printf_s("Thread %d - starting nested locked region\n", tid);  
   printf_s("Thread %d - ending nested locked region\n", tid);  
   omp_unset_nest_lock(&my_lock);  
}  
  
int main() {  
   omp_init_nest_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_nest_lock(&my_lock);  
            if (i % 3)   
               Test();  
            omp_unset_nest_lock(&my_lock);  
        }  
    }  
  
    omp_destroy_nest_lock(&my_lock);  
}  
```  
  
  **gesperrten Thread 0 \- geschachtelten Bereich beginnen**  
**Thread 0:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 0 \- geschachtelten Bereich beginnen**  
**Thread 0:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 3 \- geschachtelten Bereich beginnen**  
**Thread 3:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 3 \- geschachtelten Bereich beginnen**  
**Thread 3:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 3 \- geschachtelten Bereich beginnen**  
**Thread 3:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 2 \- geschachtelten Bereich beginnen**  
**Thread 2:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 2 \- geschachtelten Bereich beginnen**  
**Thread 2:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 2 \- geschachtelten Bereich beginnen**  
**Thread 2:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 1 \- geschachtelten Bereich beginnen**  
**Thread 1:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 1 \- geschachtelten Bereich beginnen**  
**Thread 1:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 1 \- geschachtelten Bereich beginnen**  
**Thread 1:End geschachtelter verschlossener Bereich**  
**gesperrten Thread 0 \- geschachtelten Bereich beginnen**  
**Thread 0:End geschachtelter verschlossener Bereich**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)