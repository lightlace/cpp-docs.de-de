---
title: A.23   Beispiele für die ordered-Direktive
ms.date: 11/04/2016
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
ms.openlocfilehash: 2868b771fd57613981f3c6458b48493a1b26eee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472276"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Beispiele für die ordered-Direktive

Es ist möglich, mehrere geordnete Abschnitten mit einem `for` angegeben mit der `ordered` Klausel. Im erste Beispiel ist nicht kompatibel, da die API gibt Folgendes an:

"Eine Iteration einer Schleife mit einer `for` Konstrukt muss nicht ausgeführt, die gleiche `ordered` Direktive mehr als einmal, und es muss nicht ausgeführt, mehr als eine `ordered` Richtlinie." (Finden Sie unter [Abschnitt 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite "22")

In diesem Beispiel nicht kompatible führen alle Iterationen 2 geordnete Abschnitte:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Im folgenden Beispiel von kompatiblen eine `for` mit mehr als einem sortiert Abschnitt:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```