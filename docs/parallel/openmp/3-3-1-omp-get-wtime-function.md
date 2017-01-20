---
title: "3.3.1 omp_get_wtime Function"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.1 omp_get_wtime Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_get_wtime`\-Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit auf die Wanduhr verstrichene Zeit in Sekunden zurück, da einige Zeit in der Vergangenheit „bewertet.“  Die tatsächliche „Uhrzeit in der Vergangenheit“ ist beliebig, wird jedoch nicht garantiert, um während der Ausführung der Anwendung zu ändern.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Es wird vorweggenommen, dass die Funktion verwendet wird, um geverstrichene Zeiten wie im folgenden Beispiel gezeigt messen:  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Die zurückgegebenen Vorkommen von“ Zeiten threadspezifische „betragen, das heißt ist, dass sie nicht erforderlich sind, über alle Threads globalen konsistent zu sein teilnehmend an eine Anwendung.