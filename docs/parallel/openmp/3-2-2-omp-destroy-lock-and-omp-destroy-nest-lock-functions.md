---
title: 3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19da0297844357cfbf8a0266600224bb13673b26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock- und omp_destroy_nest_lock-Funktionen
Diese Funktionen stellen sicher, dass die Spitzen beim Sperren der Variable *Sperre* ist nicht initialisiert. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Es ist nicht kompatibel, entweder diese Routinen mit einer Sperre Variablen aufzurufen, der nicht initialisiert oder entsperrt ist.