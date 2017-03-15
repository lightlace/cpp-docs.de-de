---
title: "3.2.5 omp_test_lock and omp_test_nest_lock Functions"
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
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.5 omp_test_lock and omp_test_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen versuchen, eine Sperre festzulegen Ausführung des Threads blockiert aber nicht.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Das Argument muss zu einer initialisierten Sperren variable veranschaulichen.  Diese Funktionen versuchen, eine Sperre auf die gleiche Weise wie `omp_set_lock` und `omp_set_nest_lock`festzulegen, mit dem Unterschied, dass sie werden nicht blockiert die Ausführung des Threads.  
  
 Für eine einfache Sperre `omp_test_lock` gibt die Funktion einen Wert ungleich 0 \(null\) zurück, wenn die Sperre erfolgreich festgelegt wurde. Andernfalls wird \(null\) zurück.  
  
 Für eine schachtelbare Sperre gibt die Anzahl der Schachtelungs die neue Funktion `omp_test_nest_lock` zurück, wenn die Sperre erfolgreich festgelegt wurde. Andernfalls wird \(null\) zurück.