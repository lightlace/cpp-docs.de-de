---
title: Flush (OpenMP) | Microsoft Docs
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
ms.openlocfilehash: e6933c5d74e1277b209d15aefb93a159d55f93dd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696239"
---
# <a name="flush-openmp"></a>flush (OpenMP)
Gibt an, dass alle Threads mit derselben Ansicht des Arbeitsspeichers für alle freigegebenen Objekte haben.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp flush [(var)]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `var` (optional)  
 Eine durch Trennzeichen getrennte Liste von Variablen, die Objekte darstellen, die Sie synchronisieren möchten. Wenn `var` nicht angegeben ist, werden alle Arbeitsspeicher geleert wird.  
  
## <a name="remarks"></a>Hinweise  
 Die **leeren** Richtlinie unterstützt kein OpenMP-Klauseln.  
  
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