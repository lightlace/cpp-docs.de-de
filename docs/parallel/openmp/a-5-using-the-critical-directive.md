---
title: "A.5   Using the critical Directive"
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
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.5   Using the critical Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel werden einige `critical`\-Direktive \([2.6.2 Abschnitt](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18\).  Im Beispiel wird ein Queuing Modell, in dem eine Aufgabe aus der Warteschlange entfernt und gearbeitet wird.  Um mit denen mehrere Threads zu schützen, die die gleiche Aufgabe aus der Warteschlange zu entfernen, muss der aus der Warteschlange entfernende Vorgang in einem `critical`\-Abschnitt.  Da die beiden Warteschlangen in diesem Beispiel unabhängig sind, werden sie durch `critical`\-Direktive mit unterschiedlichen Namen, *Xaxis* und *Yaxis*geschützt.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```