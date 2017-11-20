---
title: 3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c7a3aebc404205c85627820188e137713317eb7d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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