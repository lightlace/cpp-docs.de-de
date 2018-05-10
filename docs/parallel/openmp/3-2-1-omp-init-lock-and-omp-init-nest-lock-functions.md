---
title: 3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f14e182e6c981cd5de7a4cf92d8c285a4b49c66
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock-Funktionen
Diese Funktionen geben die einzige Möglichkeit, eine Sperre zu initialisieren. Jede Funktion initialisiert die Sperre dem Parameter zugeordnet *Sperre* für die Verwendung in nachfolgenden Aufrufen. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Der ursprüngliche Status ist nicht gesperrt (d. h. kein Thread die Sperre besitzt). Für omp_nest_lock_t Sperren verwenden ist der anfängliche schachteln Anzahl 0 (null). Es ist nicht kompatibel, entweder diese Routinen mit einer Sperre Variablen aufzurufen, der bereits initialisiert wurde.