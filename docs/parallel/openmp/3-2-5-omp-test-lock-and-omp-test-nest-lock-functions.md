---
title: 3.2.5 Omp_test_lock and Omp_test_nest_lock-Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5023f0b089d76e92be886f4917905f57dda7a018
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686226"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock and omp_test_nest_lock-Funktionen
Diese Funktionen versuchen, eine Sperre festzulegen, blockieren aber nicht die Ausführung des Threads. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Das Argument muss auf ein initialisiertes Sperren der Variable verweisen. Diese Funktionen versuchen, eine Sperre auf die gleiche Weise wie `omp_set_lock` und `omp_set_nest_lock`, außer dass sie nicht die Ausführung des Threads blockiert werden.  
  
 Für eine einfache Sperre der `omp_test_lock` Funktion gibt einen Wert ungleich NULL zurück, wenn die Sperre wurde erfolgreich festgelegt ist; andernfalls wird 0 (null) zurückgegeben.  
  
 Für eine omp_nest_lock_t Sperre der `omp_test_nest_lock` Funktion gibt die Anzahl die neue schachteln zurück, wenn die Sperre wurde erfolgreich festgelegt ist; andernfalls wird 0 (null) zurückgegeben.