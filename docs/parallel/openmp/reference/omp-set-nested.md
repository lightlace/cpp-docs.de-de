---
title: "omp_set_nested"
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
  - "omp_set_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nested OpenMP function"
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht geschachtelten Parallelität.  
  
## Syntax  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `val`  
 Wenn ungleich 0 \(null\), geschachtelten Parallelität aktiviert.  Wenn Null, geschachtelten Parallelität deaktiviert.  
  
## Hinweise  
 OMP\-geschachtelter Parallelität kann aktiviert werden `omp_set_nested`oder über die Befehle [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) Umgebungsvariable festgelegt wird.  
  
 Die Einstellung für `omp_set_nested` überschreibt die Einstellung der `OMP_NESTED` Umgebungsvariablen.  
  
 Wenn sie aktiviert ist, kann die Umgebungsvariable ein andernfalls operationelles Programm unterbrechen, weil die Anzahl von Threads erhöht wird, wenn sie sich exponential parallele Bereiche schachtelt.  Zum Beispiel erfordert eine Funktion, die 6mal mit der Anzahl der OMP\-Threads rekursiert, der auf 4 festgelegt werden, mit 4 \(4,096, 6\) Threads im Allgemeinen die Leistung der Anwendung beeinträchtigt, wenn die Anzahl der Threads die Anzahl der Prozessoren überschreitet.  Eine Ausnahme könnte E\/A\-gebundene Anwendungen handeln.  
  
 Verwenden Sie [omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md) , um die aktuelle Einstellung von `omp_set_nested`anzuzeigen.  
  
 Weitere Informationen finden Sie unter [3.1.9 omp\_set\_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## Beispiel  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
  **1**  
**1**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)