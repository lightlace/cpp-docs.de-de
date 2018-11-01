---
title: Verwenden von Ansichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcf4af038617cce8326a3e63ba9b4ea66c277f66
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442096"
---
# <a name="using-views"></a>Verwenden von Ansichten

Zuständigkeiten von der Ansicht sind die Daten des Dokuments für den Benutzer grafisch und zu akzeptieren und Interpretieren der Benutzereingaben als Vorgänge für das Dokument. Die Aufgaben beim Schreiben Ihrer Ansichtsklasse sind:

- Schreiben Sie Ihre Ansichtsklasse [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, die die Daten eines Dokuments gerendert wird.

- Verbinden Sie die entsprechenden Windows-Nachrichten und Benutzeroberflächen-Objekten, z. B. Menüelemente Meldungshandler-Memberfunktionen in der Ansichtsklasse.

- Implementieren Sie diese Ereignishandler zum Interpretieren der Benutzereingaben.

Darüber hinaus müssen möglicherweise andere überschreiben `CView` Member-Funktionen in Ihrer abgeleiteten Ansichtsklasse. Insbesondere möchten Sie außer Kraft setzen [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) spezielle Initialisierung für die Sicht ausführen und [OnUpdate](../mfc/reference/cview-class.md#onupdate) Sie spezielle Verarbeitung erforderlich sind, nur um die Ansicht sich selbst neu zeichnet. Bei mehrseitigen Dokumenten auch müssen Sie überschreiben [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) um das Dialogfeld "Drucken", mit der Anzahl der zu druckenden Seiten und andere Informationen zu initialisieren. Weitere Informationen zum Überschreiben `CView` Member-Funktionen, finden Sie unter Klasse [CView](../mfc/reference/cview-class.md) in die *MFC-Referenz*.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [In MFC verfügbare Abgeleitete Ansichtsklassen](../mfc/derived-view-classes-available-in-mfc.md)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

- [Interpretieren von Benutzereingaben über eine Sicht](../mfc/interpreting-user-input-through-a-view.md)

- [Die Rolle der Ansicht beim Drucken](../mfc/role-of-the-view-in-printing.md)

- [Bildlauf und Skalierung für Ansichten](../mfc/scrolling-and-scaling-views.md)

- [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)<br/>
[CFormView-Klasse](../mfc/reference/cformview-class.md)<br/>
[Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)<br/>
[Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)

