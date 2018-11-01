---
title: 3.2.4 omp_unset_lock and omp_unset_nest_lock-Funktionen
ms.date: 11/04/2016
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
ms.openlocfilehash: b0764e3590f8edb3a3e783d9b5493a64be154401
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607865"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock and omp_unset_nest_lock-Funktionen

Diese Funktionen bieten die Möglichkeit des Freigebens von den Besitz einer Sperre. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Das Argument für jede dieser Funktionen muss auf ein initialisiertes Sperren der Variable im Besitz der Threads, die Ausführung der Funktion verweisen. Wenn der Thread diese Sperre nicht besitzt, ist das Verhalten nicht definiert.

Für eine einfache Sperre die `omp_unset_lock` Funktion gibt den Thread, die Ausführung der Funktion aus den Besitz der Sperre frei.

Für eine omp_nest_lock_t-Sperre die `omp_unset_nest_lock` Funktion verringert die Anzahl der Schachtelungsebenen und Versionen der Thread, die Ausführung der Funktion aus den Besitz der Sperre, wenn das Rekursionsergebnis 0 (null) ist.