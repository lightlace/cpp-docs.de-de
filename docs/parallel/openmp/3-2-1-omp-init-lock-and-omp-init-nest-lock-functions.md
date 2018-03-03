---
title: 3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen | Microsoft Docs
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3802822465d6527e4c98a0be6a8c274d767b0f52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock-Funktionen
Diese Funktionen geben die einzige Möglichkeit, eine Sperre zu initialisieren. Jede Funktion initialisiert die Sperre dem Parameter zugeordnet *Sperre* für die Verwendung in nachfolgenden Aufrufen. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Der ursprüngliche Status ist nicht gesperrt (d. h. kein Thread die Sperre besitzt). Für omp_nest_lock_t Sperren verwenden ist der anfängliche schachteln Anzahl 0 (null). Es ist nicht kompatibel, entweder diese Routinen mit einer Sperre Variablen aufzurufen, der bereits initialisiert wurde.