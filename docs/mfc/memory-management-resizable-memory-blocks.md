---
title: 'Speicherverwaltung: Größenveränderbare Speicherblöcke | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba66fb3d85d716b18486ef08f7f2025e78d6cc57
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929329"
---
# <a name="memory-management-resizable-memory-blocks"></a>Speicherverwaltung: Größenveränderbare Speicherblöcke
Die **neue** und **löschen** Operatoren, die im Artikel beschriebenen [Speicherverwaltung: Beispiele für](../mfc/memory-management-examples.md), eignen sich für das zuordnen und Freigeben von Speicherblöcken mit fester Größe und -Objekte. In einigen Fällen kann der Anwendung Größenveränderbare Speicherblöcke erforderlich. Sie müssen die standardmäßigen Funktionen der C-Laufzeitbibliothek verwenden ["malloc"](../c-runtime-library/reference/malloc.md), [Realloc](../c-runtime-library/reference/realloc.md), und [freien](../c-runtime-library/reference/free.md) Größenveränderbare Speicherblöcke im Heap zu verwalten.  
  
> [!IMPORTANT]
>  Mischen von der **neue** und **löschen** Operatoren mit den Funktionen in der Größe veränderbaren speicherbelegung auf demselben Speicherblock führt zu beschädigten Arbeitsspeicher in der Debugversion von MFC. Verwenden Sie nicht **Realloc** auf einen Speicherblock mit zugeordneten **neue**. Ebenso sollten Sie keinen Speicherblock mit Zuweisen der **neue** Operator und löschen Sie ihn mit **freien**, oder verwenden Sie die **löschen** Operator auf einen Speicherblock zugeordnet **"malloc"**.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung: Heapbelegung](../mfc/memory-management-heap-allocation.md)

