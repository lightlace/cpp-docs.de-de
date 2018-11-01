---
title: 4.3 OMP_DYNAMIC
ms.date: 11/04/2016
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
ms.openlocfilehash: 0ea6784159a11fc194d0c1cd16d2316a80b9cd37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488564"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

Die **OMP_DYNAMIC** Umgebungsvariablen aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Bereichen verfügbar, wenn die dynamische Anpassung explizit aktiviert oder deaktiviert werden, durch den Aufruf der **Omp_set_dynamic** Bibliotheksroutine. Muss sein Wert **"true"** oder **"false"**.

Wenn auf festgelegt **"true"**, die Anzahl der Threads, die verwendet werden, für die Ausführung von paralleler Bereichen kann angepasst werden, von der Laufzeitumgebung Systemressourcen optimal zu nutzen.  Wenn auf festgelegt **"false"**, dynamische Anpassung ist deaktiviert. Die standardbedingung wird die Implementierung definiert.

Beispiel:

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- Weitere Informationen zu parallelen Bereichen, finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.