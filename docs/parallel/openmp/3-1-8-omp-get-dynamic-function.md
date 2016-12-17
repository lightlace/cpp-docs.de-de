---
title: "3.1.8 omp_get_dynamic Function"
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
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.8 omp_get_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_get\_dynamic**\-Funktion gibt einen Wert ungleich 0 \(null\), wenn dynamische Anpassung von Threads wieder aktiviert wird, und gibt andernfalls 0 zurück.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Wenn die Implementierung nicht dynamische Anpassung der Anzahl von Threads implementiert, gibt diese Funktion immer 0 zurück.  
  
## Querverweise:  
  
-   Eine Beschreibung der dynamischen Thread Farbanpassung finden Sie unter [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.