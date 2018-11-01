---
title: A.1   Parallele Ausführung einer einfachen Schleife
ms.date: 11/04/2016
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
ms.openlocfilehash: 5bd9a9c8b1d226c67f7e9031a547e551fae3407b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558937"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Parallele Ausführung einer einfachen Schleife

Im folgende Beispiel wird veranschaulicht, wie eine einfache Schleife verwenden, die parallelisiert werden die `parallel for` Richtlinie ([Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf 16). Die Iteration Schleifenvariable ist standardmäßig privat, daher es nicht notwendig ist, ihn explizit in eine private-Klausel angeben.

```
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```