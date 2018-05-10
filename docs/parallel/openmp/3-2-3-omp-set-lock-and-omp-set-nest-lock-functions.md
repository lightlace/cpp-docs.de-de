---
title: 3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba24e923051eb887db2a81c1d9765d31a4ef7b24
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock- und omp_set_nest_lock-Funktionen
Jede dieser Funktionen blockiert den Thread, die Funktion ausgeführt, bis die angegebene Sperren verfügbar ist, und dann die Sperre legt. Eine einfache Sperre ist verfügbar, wenn es entsperrt wurde. Omp_nest_lock_t-Sperre ist verfügbar, wenn es entsperrt wurde oder wenn der Thread für die Ausführung der Funktion bereits Besitzer ist. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Für eine einfache Sperre, die das Argument für die `omp_set_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Der Thread für die Ausführung der Funktion wird den Besitz der Sperre gewährt.  
  
 Für eine omp_nest_lock_t Sperre, die das Argument für die `omp_set_nest_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Die Anzahl die Schachtelungsebene wird erhöht und der Thread wird gewährt oder behält Besitz der Sperre.