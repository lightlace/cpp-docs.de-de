---
title: "Speicherverwaltung: Gr&#246;&#223;enver&#228;nderbare Speicherbl&#246;cke"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Blöcke, Speicherreservierung"
  - "Speicherreservierung, Arbeitsspeicherblockgröße"
  - "Speicherblöcke, Reservieren"
  - "Speicherblöcke, Größenveränderbar"
  - "Speicher, Beschädigung"
  - "In der Größe änderbare Arbeitsspeicherblöcke"
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherverwaltung: Gr&#246;&#223;enver&#228;nderbare Speicherbl&#246;cke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die **neu** und **löschen**, Operatoren beschrieben im Artikel [Speicherverwaltung: Beispiele](../mfc/memory-management-examples.md), sind für das Zuordnen und Freigeben von Speicherblöcken fester Größe und Objekten gut.  Gelegentlich benötigt die Anwendung voraussichtlich größenveränderbare Speicherblöcke.  Sie müssen die Standard C\-Laufzeitbibliotheksfunktionen [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md) und [frei](../c-runtime-library/reference/free.md) verwenden, um größenveränderbare Speicherblöcke auf dem Heap zu verwalten.  
  
> [!IMPORTANT]
>  Das Kombinieren der **neu** und **löschen**\-Operatoren mit den in der Größe veränderbaren Zuornungsanzahl\-Funktionen auf demselben Speicherblock ergibt beschädigten Speicher in der Debugversion von MFC.  Sie sollten `realloc` auf einen Speicherblock nicht verwenden, der mit **neu** zugeordnet wird.  Entsprechend sollten Sie einen Speicherblock mit dem Operator **neu** nicht zuordnen und diesen mit **free** löschen, oder verwenden Sie den Operator **löschen** auf einen Speicherblock, der `malloc` zugeordnet ist.  
  
## Siehe auch  
 [Speicherverwaltung: Heapbelegung](../mfc/memory-management-heap-allocation.md)