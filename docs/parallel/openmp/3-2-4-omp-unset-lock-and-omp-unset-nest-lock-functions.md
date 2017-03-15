---
title: "3.2.4 omp_unset_lock and omp_unset_nest_lock Functions"
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
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.4 omp_unset_lock and omp_unset_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen stellen eine Möglichkeit zum Freigeben des Besitz der Sperre.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Das Argument für jede dieser Funktionen müssen sich auf einen initialisierten variablen Besitzen der Sperre vom Thread verweisen, der die Funktion ausgeführt wird.  Das Verhalten ist nicht definiert, wenn der Thread nicht diese Sperre besitzt.  
  
 Für eine einfache Funktion `omp_unset_lock` die Sperre lässt der Thread, der die Funktion im Besitz der Sperre ausgeführt wird.  
  
 Für eine schachtelbare Sperren verringert die Anzahl Schachtelungs die Funktion `omp_unset_nest_lock` und die Versionen der Thread, der die Funktion im Besitz der Sperre ausgeführt wird, wenn das Rekursionsergebnis \(null\) ist.