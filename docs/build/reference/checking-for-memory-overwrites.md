---
title: Suchen nach Speicherüberschreibungen
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: ff900c7366a28d19d3b90cbd4a6d9ee732e4ce02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621558"
---
# <a name="checking-for-memory-overwrites"></a>Suchen nach Speicherüberschreibungen

Wenn Sie eine zugriffsverletzung bei einem Aufruf von Manipulation heapfunktion erhalten, ist es möglich, dass das Programm im Heap beschädigt hat. Ein häufig auftretendes Problem, diese Situation wäre:

```
Access Violation in _searchseg
```

Die [_heapchk](../../c-runtime-library/reference/heapchk.md) Funktion steht in sowohl für Debug- und Releasebuilds (nur Windows NT) zum Überprüfen der Integrität des Heaps-Bibliothek zur Laufzeit. Sie können `_heapchk` in die gleiche Weise wie der `AfxCheckMemory` Funktion, um einen Heap überschreiben, z. B. zu isolieren:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Wenn diese Funktion immer ein Fehler auftritt, müssen Sie zu isolieren, Zeitpunkt der Heap beschädigt wurde.

## <a name="see-also"></a>Siehe auch

[Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)