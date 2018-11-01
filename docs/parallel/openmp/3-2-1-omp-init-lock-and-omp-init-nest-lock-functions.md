---
title: 3.2.1 omp_init_lock and omp_init_nest_lock-Funktionen
ms.date: 11/04/2016
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
ms.openlocfilehash: 2d15aacb5e6743d18150fb45bea85b7ca22a401f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472775"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock-Funktionen

Diese Funktionen geben die einzige Möglichkeit zur Initialisierung einer Sperre. Jede Funktion initialisiert, die Sperre, die mit dem Parameter verbundenen *Sperre* für die Verwendung in nachfolgenden Aufrufen. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Der anfängliche Zustand entsperrt wird (d. h. kein Thread die Sperre besitzt). Für eine omp_nest_lock_t-Sperre ist die Anzahl die ersten Schachtelungsebene 0 (null). Es ist nicht kompatibel, um eine dieser Routinen mit einer Sperre-Variablen aufzurufen, die bereits initialisiert wurde.