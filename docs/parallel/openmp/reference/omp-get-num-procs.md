---
title: "omp_get_num_procs"
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
  - "omp_get_num_procs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_num_procs OpenMP function"
ms.assetid: 14a10b8f-e59b-4211-a292-687648c9f760
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_num_procs
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt die Anzahl der Prozessoren zurück, die verfügbar sind, wenn die Funktion aufgerufen wird.  
  
## Syntax  
  
```  
int omp_get_num_procs();  
```  
  
## Hinweise  
 Weitere Informationen finden Sie unter [3.1.5 omp\_get\_num\_procs Function](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).  
  
## Beispiel  
  
```  
// omp_get_num_procs.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    printf_s("%d\n", omp_get_num_procs( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_procs( ));  
        }  
}  
```  
  
  **\/\/\(möglicherweise in englischer Sprache\) erwartet die folgende Ausgabe, wenn das Beispiel auf einem Computer zwei Prozessoren ausgeführt wird:**  
**2**  
**2**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)