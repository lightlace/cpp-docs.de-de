---
title: "omp_get_wtime"
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
  - "omp_get_wtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_wtime OpenMP function"
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_wtime
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt den Wert der verstrichenen Zeit in Sekunden zwischen einem Punkt zurück.  
  
## Syntax  
  
```  
double omp_get_wtime( );  
```  
  
## Rückgabewert  
 Gibt einen Wert aus der verstrichenen Zeit in Sekunden, aber einige beliebige konsistentem Punkt zurück.  
  
## Hinweise  
 Dieser Punkt bleibt während der Programmausführung konsistent und ermöglicht folgende Vergleiche.  
  
 Weitere Informationen finden Sie unter [3.3.1 omp\_get\_wtime Function](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).  
  
## Beispiel  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
  **594255.3671159324 \= Start**  
**594256.3664474116 \= Fertig**  
**0.9993314791936427 \= Vergleich**  
**wtick \= 2.793651148400146e\-007**  
**1\/wtick \= 3579545**   
## Siehe auch  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)