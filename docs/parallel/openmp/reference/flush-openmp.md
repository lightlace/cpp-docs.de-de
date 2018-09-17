---
title: Flush (OpenMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Flush
dev_langs:
- C++
helpviewer_keywords:
- flush OpenMP directive
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ea89d4feb7a554c2495c11aa8acaeeaa8bc775f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722058"
---
# <a name="flush-openmp"></a>flush (OpenMP)
Gibt an, dass alle Threads die gleiche Ansicht der Arbeitsspeicher für alle freigegebenen Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp flush [(var)]  
```  
  
## <a name="arguments"></a>Argumente

*var*<br/>
(Optional) Eine durch Trennzeichen getrennte Liste von Variablen, die Objekte darstellen, die Sie synchronisieren möchten. Wenn `var` nicht angegeben ist, alle Arbeitsspeicher wird geleert.  
  
## <a name="remarks"></a>Hinweise  
 Die **leeren** -Anweisung unterstützt keine OpenMP-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.5 flush-Direktive](../../../parallel/openmp/2-6-5-flush-directive.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
```Output  
Thread 0: read data  
Thread 1: process data  
data = 2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)