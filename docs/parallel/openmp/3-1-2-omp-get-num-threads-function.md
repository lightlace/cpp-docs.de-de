---
title: 3.1.2 omp_get_num_threads-Funktion
ms.date: 11/04/2016
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
ms.openlocfilehash: 587b49f70896bcfe8c1a805a4ebb13a11e9bb7d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465246"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads-Funktion

Die **Omp_get_num_threads** Funktion gibt die Anzahl der Threads derzeit im Team, das Ausführen des parallelen Bereichs, der von dem es aufgerufen wird. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_num_threads(void);
```

Die **Num_threads** -Klausel, die **Omp_set_num_threads** -Funktion, und die **OMP_NUM_THREADS** Umgebungsvariable steuern die Anzahl der Threads in einem Team.

Wenn die Anzahl der Threads explizit nicht vom Benutzer festgelegt wurde, ist die Standardeinstellung Implementierung definiert. Diese Funktion für die nächste einschließende bindet **parallele** Richtlinie. Wenn Sie aufgerufen wird, über einen seriellen Teil eines Programms oder eines geschachtelten parallelen Bereichs, das serialisiert wird, gibt diese Funktion 1 zurück.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **OMP_NUM_THREADS** Umgebung Variablen, finden Sie unter [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf 48.

- **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **Parallele** erstellen, finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.