---
title: 3.2.1 Omp_init_lock and Omp_init_nest_lock-Funktionen | Microsoft-Dokumentation
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
ms.openlocfilehash: 4303eb3ccfcb1c449022a4be32f94b9f91e6e80c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387002"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock-Funktionen

Diese Funktionen geben die einzige Möglichkeit zur Initialisierung einer Sperre. Jede Funktion initialisiert, die Sperre, die mit dem Parameter verbundenen *Sperre* für die Verwendung in nachfolgenden Aufrufen. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Der anfängliche Zustand entsperrt wird (d. h. kein Thread die Sperre besitzt). Für eine omp_nest_lock_t-Sperre ist die Anzahl die ersten Schachtelungsebene 0 (null). Es ist nicht kompatibel, um eine dieser Routinen mit einer Sperre-Variablen aufzurufen, die bereits initialisiert wurde.