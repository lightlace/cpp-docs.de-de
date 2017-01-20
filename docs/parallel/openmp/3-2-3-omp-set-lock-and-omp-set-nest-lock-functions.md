---
title: "3.2.3 omp_set_lock and omp_set_nest_lock Functions"
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
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.3 omp_set_lock and omp_set_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Jede dieser Funktionen blockiert den Thread, der die Funktion ausführt, bis die angegebene Sperre verfügbar ist, und legt dann die Sperre fest.  Eine einfache Zuweisung ist verfügbar, wenn sie aufgehoben wurde.  Eine schachtelbare Sperre aufgehoben, wenn sie verfügbar ist, wird oder wenn sie bereits von dem Thread gehört, der die Funktion ausgeführt wird.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Für eine einfache Sperre muss das Argument für die Funktion einer initialisierten Sperren `omp_set_lock`\-Variable verweisen.  Besitz der Sperre wurde erteilt dem Thread, der die Funktion ausgeführt wird.  
  
 Für eine schachtelbare Sperre muss das Argument für die Funktion einer initialisierten Sperren `omp_set_nest_lock`\-Variable verweisen.  Die Anzahl der Schachtelungs wird erhöht, und der Thread erteilt oder verwaltet, den Besitz der Sperre.