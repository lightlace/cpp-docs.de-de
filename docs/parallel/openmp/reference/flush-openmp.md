---
title: "flush (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Flush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flush OpenMP directive"
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# flush (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass alle Threads die gleiche Ansicht des Arbeitsspeichers für alle freigegebenen Objekte haben.  
  
## Syntax  
  
```  
#pragma omp flush [(var)]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var` \(optional\)  
 Eine durch Trennzeichen getrennte Liste von Variablen, die Objekte darstellen möchten Sie synchronisieren.  Wenn `var` nicht angegeben ist, wird der gesamte Speicherplatz geleert.  
  
## Hinweise  
 Die **leer**\-Direktiven unterstützen keine OpenMP\-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.5 flush Directive](../../../parallel/openmp/2-6-5-flush-directive.md).  
  
## Beispiel  
  
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
  
  **Thread 0: Lesen von Daten**  
**Thread 1: Verarbeiten von Daten**  
**2 \= Daten**   
## Siehe auch  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)