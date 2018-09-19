---
title: Überprüfung auf Speicherüberschreibung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 246f625e899016080662f27a5901962c1c62f1a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718642"
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