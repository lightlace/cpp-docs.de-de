---
title: A.5   Verwenden der critical-Direktive
ms.date: 11/04/2016
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
ms.openlocfilehash: 82497d63acc057fbbcf26f585e42fc8611c08ec4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545097"
---
# <a name="a5---using-the-critical-directive"></a>A.5   Verwenden der critical-Direktive

Das folgende Beispiel schließt mehrere `critical` Directives ([Abschnitt 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18). Das Beispiel veranschaulicht ein Warteschlangen-Modell, bei der eine Aufgabe aus der Warteschlange entfernt und bearbeitet, werden. Um für mehrere Threads, die aus der Warteschlange entfernt der gleichen Aufgabe zu schützen, muss der entfernen-Vorgang einem `critical` Abschnitt. Da die zwei Warteschlangen in diesem Beispiel unabhängig sind, werden sie durch geschützt `critical` Anweisungen mit unterschiedlichen Namen *x-Achse enthält* und *Yaxis*.

```
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```