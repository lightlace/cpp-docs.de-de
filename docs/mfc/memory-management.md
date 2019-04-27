---
title: Speicherverwaltung
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: 1c7f901009d5e1e7f0af20d493bb748b46b18480
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219128"
---
# <a name="memory-management"></a>Speicherverwaltung

Dieser Gruppe von Artikeln wird beschrieben, wie Sie von der Microsoft Foundation Class-Bibliothek (MFC) im Zusammenhang mit der Speicherverwaltung über die allgemeinen Dienste nutzen können. Speicherbelegung kann in zwei Hauptkategorien unterteilt werden: frame-Zuordnungen und Heap-Zuordnungen.

Ein Hauptunterschied zwischen den zwei Zuordnung Techniken ist, dass die Frame-Zuordnung, die Sie in der Regel mit den tatsächlichen Arbeitsspeicher arbeiten, zu blockieren, während mit Heapzuordnung Sie immer einen Zeiger zum Speicherblock erhalten. Eine andere Hauptunterschied zwischen den beiden Schemas ist, dass der Keyframe-Objekte automatisch gelöscht werden, während die Heap-Objekte explizit gelöscht werden müssen, können Sie durch den Programmierer.

MFC-fremde Informationen zur Verwaltung des Arbeitsspeichers in Programmen für Windows finden Sie [Speicherverwaltung](/windows/desktop/memory/memory-management) im Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Rahmenzuordnung](../mfc/memory-management-frame-allocation.md)

- [Heapzuordnung](../mfc/memory-management-heap-allocation.md)

- [Zuordnen von Speicher für ein array](../mfc/memory-management-examples.md)

- [Freigeben von Speicher für ein Array aus dem heap](../mfc/memory-management-examples.md)

- [Zuweisen von Arbeitsspeicher für eine Datenstruktur](../mfc/memory-management-examples.md)

- [Zuordnen von Speicher für ein Objekt](../mfc/memory-management-examples.md)

- [Größenveränderbare Speicherblöcke](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
