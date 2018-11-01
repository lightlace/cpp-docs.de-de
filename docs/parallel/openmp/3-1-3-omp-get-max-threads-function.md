---
title: 3.1.3 omp_get_max_threads-Funktion
ms.date: 11/04/2016
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
ms.openlocfilehash: 3f954b5ad75b4bdb4a74323f2ab4e819850269ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546581"
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads-Funktion

Die **Omp_get_max_threads** Funktionsergebnis ist eine ganze Zahl, die garantiert ist, muss mindestens so groß wie die Anzahl von Threads, die verwendet wird, um ein Team zu bilden, wenn einem parallelen Bereich ohne eine **Num_threads** Klausel an diesem Punkt im Code auftreten würden. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_max_threads(void);
```

Die folgenden drückt eine untere Grenze aus, auf dem Wert des **Omp_get_max_threads**:

```

threads-used-for-next-team
<= omp_get_max_threads

```

Beachten Sie, dass, wenn eine nachfolgende parallelen Bereichs verwendet die **Num_threads** -Klausel, um eine bestimmte Anzahl von Threads, die Garantie für die untere Grenze des Ergebnisses der Anforderung **Omp_get_max_threads** keine langen enthält.

Die **Omp_get_max_threads** Rückgabewert der Funktion zum dynamischen Zuweisen von ausreichend Speicherplatz für alle Threads im Team gebildet, die in der nachfolgenden parallele Region verwendet werden kann.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Omp_get_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.

- **Omp_set_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf 36.

- **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.

- **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.