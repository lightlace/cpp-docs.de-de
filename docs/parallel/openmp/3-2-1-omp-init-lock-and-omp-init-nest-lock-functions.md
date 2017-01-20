---
title: "3.2.1 omp_init_lock and omp_init_nest_lock Functions"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.1 omp_init_lock and omp_init_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen stellen das einzige eine Möglichkeit zum Initialisieren einer Sperre.  Jede Funktion initialisiert die Sperre, die der Parameter *sperre* für die Verwendung bei nachfolgenden Aufrufen zugeordnet ist.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Der Ausgangszustand entsperrt wird \(das heißt besitzt kein Thread die Sperre\).  Für eine schachtelbare Sperre ist die ursprüngliche Schachtelungs für die Anzahl Nullen.  Sie ist inkompatibel, dass diese Routinen mit einer Sperre variable aufzurufen, die bereits initialisiert wurde.