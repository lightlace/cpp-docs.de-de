---
title: Die Verwaltung des Arbeitsspeichers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928a954be6a96f5026a98f724a77bebd51be27f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345077"
---
# <a name="memory-management"></a>Speicherverwaltung
Diese Gruppe von Artikeln wird beschrieben, wie die allgemeinen Dienste von der Microsoft Foundation Class-Bibliothek (MFC) im Zusammenhang mit der Verwaltung des Arbeitsspeichers nutzen wird. Speicherbelegung kann in zwei Hauptkategorien unterteilt werden: Zuordnungen und Heapzuordnungen frame.  
  
 Ein Hauptunterschied zwischen den beiden Zuordnung Techniken ist, dass mit Frame Zuordnungseinheiten, die Sie in der Regel mit den tatsächlichen Arbeitsspeicher arbeiten selbst zu blockieren, während mit Heapzuordnung Sie immer einen Zeiger zum Speicherblock Dateinamenangabe. Eine andere Hauptunterschied zwischen den beiden Schemas ist, dass die Frame-Objekten automatisch gelöscht werden, während Heapobjekte explizit vom Programmierer gelöscht werden müssen.  
  
 MFC-fremde Informationen zur Verwaltung des Arbeitsspeichers in Programmen für Windows finden Sie unter [Speicherverwaltung](http://msdn.microsoft.com/library/windows/desktop/aa366779) im Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Rahmenzuordnung](../mfc/memory-management-frame-allocation.md)  
  
-   [Heapzuordnung](../mfc/memory-management-heap-allocation.md)  
  
-   [Belegen von Speicher für ein array](../mfc/memory-management-examples.md)  
  
-   [Freigeben von Speicher für ein Array aus dem heap](../mfc/memory-management-examples.md)  
  
-   [Belegen von Speicher für eine Datenstruktur](../mfc/memory-management-examples.md)  
  
-   [Belegen von Speicher für ein Objekt](../mfc/memory-management-examples.md)  
  
-   [Größenveränderbare Speicherblöcke](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

