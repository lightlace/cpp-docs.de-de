---
title: Omp_init_nest_lock | Microsoft-Dokumentation
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
ms.openlocfilehash: 11c3e0fc08f8c2e0f4df9ac20df6260f64618ee3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029545"
---
# <a name="ompinitnestlock"></a>omp_init_nest_lock
Initialisiert eine Sperre an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_init_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>Parameter 
  
*lock*<br/>
Eine Variable vom Typ [aufgerufen](../../../parallel/openmp/reference/omp-nest-lock-t.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl die ersten Schachtelungsebene ist 0 (null).  
  
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