---
title: 3.2.3 omp_set_lock- und omp_set_nest_lock-Funktionen
ms.date: 11/04/2016
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
ms.openlocfilehash: 8efc1f844be2d1b8cf9b15242758914edd0fca14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617658"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock- und omp_set_nest_lock-Funktionen

Jede dieser Funktionen blockiert den Thread, die Funktion ausgeführt, bis die angegebene Sperre verfügbar ist, und dann die Sperre legt. Eine einfache Sperre ist verfügbar, wenn es nicht gesperrt ist. Omp_nest_lock_t-Sperre ist verfügbar, wenn es nicht gesperrt ist oder wenn sie bereits den Thread, die Ausführung der Funktion gehört. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Für eine einfache Sperre, die das Argument für die `omp_set_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Der Thread, die Ausführung der Funktion wird den Besitz der Sperre gewährt.

Für eine omp_nest_lock_t-Sperre, das Argument für die `omp_set_nest_lock` Funktion muss auf ein initialisiertes Sperren der Variable verweisen. Die Anzahl die Schachtelungsebene wird erhöht, und den Thread erhält, oder behält den Besitz der Sperre.