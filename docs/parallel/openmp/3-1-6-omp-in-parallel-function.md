---
title: "3.1.6 omp_in_parallel Function"
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
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.6 omp_in_parallel Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_in\_parallel**\-Funktion gibt einen Wert ungleich 0 \(null\) zurück, wenn sie innerhalb des dynamischen Wertebereichs eines parallelen Bereichs aufgerufen wird, der parallel ausgeführt werden. Andernfalls wird 0 zurückgegeben.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Diese Funktion gibt einen Wert ungleich 0 \(null\) zurück, wenn sie aus einem Bereich aufgerufen wird, der parallel, einschließlich geschachtelter Panel\-Elemente ausführt, die serialisiert werden.