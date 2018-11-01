---
title: A.4   Verwenden der nowait-Klausel
ms.date: 11/04/2016
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
ms.openlocfilehash: 7f839397787c35e88ea325c2db81b15b3a4e7508
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454924"
---
# <a name="a4---using-the-nowait-clause"></a>A.4   Verwenden der nowait-Klausel

Wenn mehrere unabhängige Schleifen innerhalb eines parallelen Bereichs vorhanden sind, können Sie mithilfe der `nowait` Klausel ([Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite 11), vermeiden Sie die implizite Grenze am Ende der `for` Anweisung wie folgt:

```
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```