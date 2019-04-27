---
title: 'Speicherverwaltung: Größenveränderbare Speicherblöcke'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: 124a2599e1523d5393fcf6255c88de0fd8cd72cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219141"
---
# <a name="memory-management-resizable-memory-blocks"></a>Speicherverwaltung: Größenveränderbare Speicherblöcke

Die **neue** und **löschen** Operatoren, die in diesem Artikel beschriebenen [Speicherverwaltung: Beispiele für](../mfc/memory-management-examples.md), eignen sich für das zuordnen und Freigeben von Speicherblöcken mit fester Größe und Objekte. In einigen Fällen möglicherweise Ihre Anwendung Größenveränderbare Speicherblöcke. Sie müssen die Funktionen der standard C-Laufzeitbibliothek verwenden [Malloc](../c-runtime-library/reference/malloc.md), [Realloc](../c-runtime-library/reference/realloc.md), und [kostenlose](../c-runtime-library/reference/free.md) Größenveränderbare Speicherblöcke im Heap zu verwalten.

> [!IMPORTANT]
>  Das Kombinieren von der **neue** und **löschen** beschädigter Arbeitsspeicher in der Debugversion des MFC-Operatoren mit den Funktionen in der Größe veränderbaren speicherbelegung auf demselben Speicherblock führen. Verwenden Sie nicht **Realloc** auf einen Speicherblock zugeordnet **neue**. Ebenso sollten Sie keinen Speicherblock mit Zuweisen der **neue** Operator und löschen Sie ihn mit **kostenlose**, oder verwenden Sie die **löschen** Operator auf einen Speicherblock zugeordnet**Malloc**.

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung: Heapzuordnung](../mfc/memory-management-heap-allocation.md)
