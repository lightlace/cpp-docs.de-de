---
title: Omp_init_nest_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_init_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_init_nest_lock OpenMP function
ms.assetid: cf749ec5-de78-4186-9588-ac7c42b02463
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca97885a64df3897bda59dd7f04b2306f31536aa
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692950"
---
# <a name="ompinitnestlock"></a>omp_init_nest_lock
Initialisiert eine Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_init_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `lock`  
 Eine Variable vom Typ [aufgerufen](../../../parallel/openmp/reference/omp-nest-lock-t.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl die anfänglichen Schachtelung ist 0 (null).  
  
 Weitere Informationen finden Sie unter [3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)