---
title: "omp_set_dynamic"
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
  - "omp_set_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_dynamic OpenMP function"
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die Anzahl der Threads, die im Folgenden parallelen Bereich verfügbar sind, von der Laufzeit angepasst werden kann.  
  
## Syntax  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `val`  
 Ein Wert, der angibt, ob die Anzahl der Threads, die im Folgenden parallelen Bereich verfügbar sind, von der Laufzeit angepasst werden kann.  Wenn ungleich 0 \(null\), die Common Language Runtime die Anzahl der Threads angepasst werden kann, wenn nicht null, die Laufzeit dynamisch die Anzahl der Threads an.  
  
## Hinweise  
 Die Anzahl von Threads überschreitet keinesfalls den Wert, der von [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder durch [OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)festgelegt ist.  
  
 Verwenden Sie [omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) , um die aktuelle Einstellung von `omp_set_dynamic`anzuzeigen.  
  
 Die Einstellung für `omp_set_dynamic` überschreibt die Einstellung der [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) Umgebungsvariablen.  
  
 Weitere Informationen finden Sie unter [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Beispiel  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
  **1**  
**1**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)