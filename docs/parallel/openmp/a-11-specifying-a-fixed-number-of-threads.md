---
title: A.11   Angeben einer festgelegten Anzahl von Threads
ms.date: 11/04/2016
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
ms.openlocfilehash: 832afac9abc7edd03d3af6f567657aefd596aae0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492042"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Angeben einer festgelegten Anzahl von Threads

Einige Programme sind abhängig von einer festen, vordefinierten Anzahl von Threads ordnungsgemäß ausgeführt wird.  Da die Standardeinstellung für die dynamische Anpassung der Anzahl von Threads Implementierung definiert ist, können diese Programme deaktivieren Sie die dynamische Threads-Funktion, und legen Sie die Anzahl der Threads explizit um die Portabilität sicherzustellen. Das folgende Beispiel zeigt, wie Sie dazu `omp_set_dynamic` ([Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39), und `omp_set_num_threads` ([Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf 36):

```
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

In diesem Beispiel führt das Programm ordnungsgemäß nur dann, wenn es von 16 Threads ausgeführt wird. Ist die Implementierung nicht 16 Threads unterstützen kann, wird das Verhalten der in diesem Beispiel wird mit der Implementierung definiert.

Beachten Sie, dass die Anzahl der Threads, die Ausführung eines parallelen Bereichs während eines parallelen Bereichs ist, unabhängig von der Einstellung "Threads" dynamische konstant bleibt. Der Mechanismus für die dynamische Threads bestimmt die Anzahl der Threads an, zu Beginn des parallelen Bereichs verwendet und für die Dauer des Bereichs konstant bleibt.