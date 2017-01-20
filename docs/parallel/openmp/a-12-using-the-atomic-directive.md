---
title: "A.12   Using the atomic Directive"
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
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.12   Using the atomic Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel werden Racebedingungen \(gleichzeitige Aktualisierungen eines Elements durch mehrere Threads von *x* \) durch die `atomic`\-Direktive \([2.6.4 Abschnitt](../../parallel/openmp/2-6-4-atomic-construct.md) auf Seite 19\):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 Der Vorteil der Verwendung der `atomic`\-Direktive in diesem Beispiel besteht darin, dass Aktualisierungen von zwei verschiedenen Elementen von x ermöglicht, dass parallel ausgeführt.  Wenn `critical`\-Direktive \([2.6.2 Abschnitt](../../parallel/openmp/2-6-2-critical-construct.md) stattdessen auf Seite 18\) verwendet wurden, dann würden alle Aktualisierungen auf die Elemente von *x* seriell ausgeführt \(obwohl nicht in einer garantierten Reihenfolge\).  
  
 Beachten Sie, dass die `atomic`\-Direktive nur für C\- oder C\+\+\-Anweisung unmittelbar nach deren gelten.  Daher werden atomar *y* von Elementen in diesem Beispiel nicht aktualisiert.