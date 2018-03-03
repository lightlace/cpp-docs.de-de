---
title: 3.2.5 Omp_test_lock and Omp_test_nest_lock-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fcdacdbb38a9bb27e35ada74aa2139be10c6797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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