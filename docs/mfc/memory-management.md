---
title: Speicherverwaltung | Microsoft-Dokumentation
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
ms.openlocfilehash: 28191191572e508828a23f0e719a57d63163b08d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222350"
---
# <a name="memory-management"></a>Speicherverwaltung
Dieser Gruppe von Artikeln wird beschrieben, wie Sie von der Microsoft Foundation Class-Bibliothek (MFC) im Zusammenhang mit der Speicherverwaltung über die allgemeinen Dienste nutzen können. Speicherbelegung kann in zwei Hauptkategorien unterteilt werden: frame-Zuordnungen und Heap-Zuordnungen.  
  
 Ein Hauptunterschied zwischen den zwei Zuordnung Techniken ist, dass die Frame-Zuordnung, die Sie in der Regel mit den tatsächlichen Arbeitsspeicher arbeiten, zu blockieren, während mit Heapzuordnung Sie immer einen Zeiger zum Speicherblock erhalten. Eine andere Hauptunterschied zwischen den beiden Schemas ist, dass der Keyframe-Objekte automatisch gelöscht werden, während die Heap-Objekte explizit gelöscht werden müssen, können Sie durch den Programmierer.  
  
 MFC-fremde Informationen zur Verwaltung des Arbeitsspeichers in Programmen für Windows finden Sie [Speicherverwaltung](https://msdn.microsoft.com/library/windows/desktop/aa366779) im Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Rahmenzuordnung](../mfc/memory-management-frame-allocation.md)  
  
-   [Heapzuordnung](../mfc/memory-management-heap-allocation.md)  
  
-   [Zuordnen von Speicher für ein array](../mfc/memory-management-examples.md)  
  
-   [Freigeben von Speicher für ein Array aus dem heap](../mfc/memory-management-examples.md)  
  
-   [Zuweisen von Arbeitsspeicher für eine Datenstruktur](../mfc/memory-management-examples.md)  
  
-   [Zuordnen von Speicher für ein Objekt](../mfc/memory-management-examples.md)  
  
-   [Größenveränderbare Speicherblöcke](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

