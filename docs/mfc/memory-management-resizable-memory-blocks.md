---
title: "Speicherverwaltung: Größenveränderbare Speicherblöcke | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fce06d27a091ad1740c882367358cf69a6dc3e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-resizable-memory-blocks"></a>Speicherverwaltung: Größenveränderbare Speicherblöcke
Die **neue** und **löschen** Operatoren, die im Artikel beschriebenen [Speicherverwaltung: Beispiele für](../mfc/memory-management-examples.md), eignen sich für das zuordnen und Freigeben von Speicherblöcken mit fester Größe und -Objekte. In einigen Fällen kann der Anwendung Größenveränderbare Speicherblöcke erforderlich. Sie müssen die standardmäßigen Funktionen der C-Laufzeitbibliothek verwenden ["malloc"](../c-runtime-library/reference/malloc.md), [Realloc](../c-runtime-library/reference/realloc.md), und [freien](../c-runtime-library/reference/free.md) Größenveränderbare Speicherblöcke im Heap zu verwalten.  
  
> [!IMPORTANT]
>  Mischen von der **neue** und **löschen** Operatoren mit den Funktionen in der Größe veränderbaren speicherbelegung auf demselben Speicherblock führt zu beschädigten Arbeitsspeicher in der Debugversion von MFC. Verwenden Sie nicht `realloc` auf einen Speicherblock mit zugeordneten **neue**. Ebenso sollten Sie keinen Speicherblock mit Zuweisen der **neue** Operator und löschen Sie ihn mit **freien**, oder verwenden Sie die **löschen** Operator auf einen Speicherblock zugeordnet`malloc`.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung: Heapbelegung](../mfc/memory-management-heap-allocation.md)

