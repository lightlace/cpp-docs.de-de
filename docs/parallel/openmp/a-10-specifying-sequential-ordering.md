---
title: "A.10   Specifying Sequential Ordering"
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
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.10   Specifying Sequential Ordering
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Geordnete Abschnitte \([2.6.6 Abschnitt](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite 22\) sind für die Ausgabe der Arbeit Reihenfolge sortieren, die parallel ausgeführt wird.  Das folgende Programm druckt die Indizes der in sequenzieller Reihenfolge aus:  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```