---
title: 3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e709e43a0b32b68bc34c4e76e8680ae371e30670
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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