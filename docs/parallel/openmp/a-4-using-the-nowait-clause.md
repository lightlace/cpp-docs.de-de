---
title: "A.4   Using the nowait Clause"
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
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.4   Using the nowait Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn mehrere Schleifen unabhängige innerhalb eines parallelen Bereichs vorhanden sind, können Sie die `nowait` Clause \([2.4.1 Abschnitt](../../parallel/openmp/2-4-1-for-construct.md) auf Seite 11\) verwenden, um die implizite Grenze am Ende der `for`\-Direktive zu vermeiden:  
  
```  
#pragma omp parallel  
{  
    #pragma omp for nowait  
        for (i=1; i<n; i++)  
             b[i] = (a[i] + a[i-1]) / 2.0;  
    #pragma omp for nowait  
        for (i=0; i<m; i++)  
            y[i] = sqrt(z[i]);  
}  
```