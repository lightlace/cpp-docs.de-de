---
title: A. 6 Verwenden der Lastprivate-Klausel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d18d3aaf5c5d1cbe03282710ae4f4e2bb613f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390577"
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