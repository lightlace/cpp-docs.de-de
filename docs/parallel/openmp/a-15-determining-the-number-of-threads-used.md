---
title: "A.15   Determining the Number of Threads Used"
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
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.15   Determining the Number of Threads Used
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Betrachten Sie das folgende Beispiel der falschen \(für [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37\):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 Die `omp_get_num_threads()` Rückkehraufrufe 1 im seriellen Codeabschnitt, sodass *NP* sind immer gleich 1 im vorherigen Beispiel.  Um die Anzahl der Threads ermitteln möchten, die für den bereitgestellten parallelen Bereich muss der Aufruf innerhalb des parallelen Bereichs.  
  
 Das folgende Beispiel zeigt, wie Sie das Programm neu geschrieben werden, ohne eine Abfrage einzuschließenden für die Anzahl von Threads:  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```