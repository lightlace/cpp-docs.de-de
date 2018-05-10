---
title: 3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f480a75efff737356c1477593e182537ae73a8c8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock and omp_unset_nest_lock-Funktionen
Diese Funktionen bieten die Möglichkeit des Freigebens von Besitz einer Sperre. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Das Argument für jede dieser Funktionen muss auf ein initialisiertes Sperren der Variable im Besitz der Thread für die Ausführung der Funktion verweisen. Das Verhalten ist undefiniert, wenn der Thread diese Sperre nicht besitzt.  
  
 Für eine einfache Sperre der `omp_unset_lock` Funktion gibt der Thread für die Ausführung der Funktion aus den Besitz der Sperre frei.  
  
 Für eine omp_nest_lock_t Sperre der `omp_unset_nest_lock` Funktion verringert die Anzahl der Schachtelungsebenen und Versionen der Thread, der die Funktion aus den Besitz der Sperre ausgeführt wird, wenn das Rekursionsergebnis 0 (null) ist.