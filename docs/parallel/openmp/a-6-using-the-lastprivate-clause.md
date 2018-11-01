---
title: A.6   Verwenden der lastprivate-Klausel
ms.date: 11/04/2016
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
ms.openlocfilehash: 7d5ba1413827590b7fb3afa0847b9aa1da3c41e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579803"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   Verwenden der lastprivate-Klausel

Manchmal die richtige Ausführung hängt von der Wert, den die letzte Iteration einer Schleife zu einer Variablen zugewiesen. Diese Programme sind, müssen alle diese Variablen als Argumente für Auflisten einer `lastprivate` Klausel ([Abschnitt 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) auf Seite "27"), damit die Werte der Variablen werden bei Ausführung der Schleife sequenziell ist identisch.

```
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

Im vorherigen Beispiel den Wert der `i` am Ende des parallelen Bereichs ist gleich `n-1`, wie im sequentiell.