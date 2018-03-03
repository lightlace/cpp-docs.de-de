---
title: 3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen | Microsoft Docs
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
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d0b91fd311581235a893a0b3f4f383e724f9aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock- und omp_destroy_nest_lock-Funktionen
Diese Funktionen stellen sicher, dass die Spitzen beim Sperren der Variable *Sperre* ist nicht initialisiert. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Es ist nicht kompatibel, entweder diese Routinen mit einer Sperre Variablen aufzurufen, der nicht initialisiert oder entsperrt ist.