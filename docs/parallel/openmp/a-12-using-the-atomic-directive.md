---
title: A.12   Verwenden der atomic-Direktive
ms.date: 11/04/2016
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
ms.openlocfilehash: 0f75b182e2cae11f0e72d5ca1e67f887294e8f69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504436"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Verwenden der atomic-Direktive

Im folgende Beispiel vermeidet Racebedingungen (gleichzeitige Aktualisierungen eines Elements von *x* von mehreren Threads) mithilfe der `atomic` Richtlinie ([Abschnitt 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) auf 19):

```
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Der Vorteil der Verwendung der `atomic` -Anweisung in diesem Beispiel ist, dass es ermöglicht, dass Updates von zwei verschiedenen Elementen von x parallel ausgeführt. Wenn eine `critical` Richtlinie ([Abschnitt 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18) stattdessen verwendet wurden, und klicken Sie dann alle updates auf Elemente des *x* seriell (jedoch nicht in einer Reihenfolge garantiert) ausgeführt.

Beachten Sie, dass die `atomic` Richtlinie gilt nur für die C- oder C++-Anweisung, die unmittelbar folgt.  Als Ergebnis Elemente *y* in diesem Beispiel werden nicht automatisch aktualisiert.