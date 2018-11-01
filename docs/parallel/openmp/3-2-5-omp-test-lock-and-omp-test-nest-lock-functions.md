---
title: 3.2.5 omp_test_lock and omp_test_nest_lock-Funktionen
ms.date: 11/04/2016
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
ms.openlocfilehash: e8e03699f807f23f139075560592d8846467f2c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512749"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock and omp_test_nest_lock-Funktionen

Diese Funktionen versuchen, eine Sperre festzulegen, blockieren aber nicht die Ausführung des Threads. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Das Argument muss auf ein initialisiertes Sperren der Variable verweisen. Diese Funktionen versuchen, eine Sperre auf die gleiche Weise wie festgelegt `omp_set_lock` und `omp_set_nest_lock`, außer dass sie nicht die Ausführung des Threads blockiert werden.

Für eine einfache Sperre die `omp_test_lock` Funktion gibt einen Wert ungleich NULL zurück, wenn die Sperre erfolgreich festgelegt wurde; andernfalls wird 0 (null) zurückgegeben.

Für eine omp_nest_lock_t-Sperre die `omp_test_nest_lock` Funktion gibt die Anzahl die neue schachteln zurück, wenn die Sperre erfolgreich festgelegt wurde; andernfalls wird 0 (null) zurückgegeben.