---
title: 3.1.4 omp_get_thread_num-Funktion
ms.date: 11/04/2016
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
ms.openlocfilehash: eca8522aeab4702be390d98faaf8920f2d732244
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480930"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num-Funktion

Die `omp_get_thread_num` Funktion gibt die Thread-Anzahl, innerhalb der Teams, die Threads, die Ausführung der Funktion. Die Thread-Anzahl liegt zwischen 0 und **omp_get_num_threads()**-1 (einschließlich). Die master-Thread des Teams ist Thread 0.

Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_thread_num(void);
```

Wenn über eine serielle Region aufgerufen `omp_get_thread_num` gibt 0 zurück. Wenn Sie von innerhalb eines geschachtelten parallelen Bereichs aufgerufen, die serialisiert wird, gibt diese Funktion 0 zurück.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- `omp_get_num_threads` funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.