---
title: A.15   Ermitteln der Anzahl von verwendeten Threads
ms.date: 11/04/2016
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
ms.openlocfilehash: bd5e897eeab35ec73c061d2ae02a4b85772e1255
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525833"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Ermitteln der Anzahl von verwendeten Threads

Betrachten Sie die folgende falsche Beispiel (für [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37):

```
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

Die `omp_get_num_threads()` aufrufen, gibt 1 zurück im seriellen Abschnitt des Codes, also *Np* wird immer im vorherigen Beispiel gleich 1 sein. Um die Anzahl der Threads zu bestimmen, die für den parallelen Bereich bereitgestellt werden, sollte der Aufruf in den parallelen Bereich sein.

Das folgende Beispiel zeigt, wie Sie dieses Programm zu schreiben, ohne dass eine Abfrage für die Anzahl der Threads:

```
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```