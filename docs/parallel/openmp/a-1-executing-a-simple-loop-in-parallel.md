---
title: "A.1   Executing a Simple Loop in Parallel"
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
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.1   Executing a Simple Loop in Parallel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird veranschaulicht, wie eine einfache Schleife parallelisiert mithilfe der `parallel for`\-Direktive auf[2.5.1 Abschnitt](../../parallel/openmp/2-5-1-parallel-for-construct.md) \(Seite 16\).  Die Schleifeniterationsvariable ist standardmäßig privat. Es ist daher nicht erforderlich, diese in einer privaten \- Klausel explizit anzugeben.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```