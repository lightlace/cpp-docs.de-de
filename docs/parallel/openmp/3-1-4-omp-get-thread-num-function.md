---
title: "3.1.4 omp_get_thread_num Function"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.4 omp_get_thread_num Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_get_thread_num`\-Funktion gibt die Anzahl von Threads innerhalb des Teams zurück, des Threads die Funktion.  Die Thread Zahl liegt zwischen 0 und einschließlich 1 – **omp\_get\_num\_threads \(\)**.  Der Masterthread des Teams Thread 0 ist.  
  
 Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 Wenn es von einem seriellen Bereich aufgerufen wird, gibt `omp_get_thread_num` 0 zurück.  Wenn sie aus einem geschachtelten parallelen Bereich aufgerufen wird, der serialisiert wird, gibt die Funktion 0 zurück.  
  
## Verweist auf:  
  
-   `omp_get_num_threads`\-Funktion finden [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.