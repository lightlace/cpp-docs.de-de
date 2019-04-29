---
title: Initialisieren und Bereinigen von Dokumenten und Ansichten
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
ms.openlocfilehash: 59e86f4000e2da588749ca48887d34c3effdfc3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297189"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Initialisieren und Bereinigen von Dokumenten und Ansichten

Verwenden Sie die folgenden Richtlinien für das Initialisieren und Bereinigen nach Dokumenten und Ansichten aus:

- MFC-Framework initialisiert, Dokumenten und Ansichten. Sie initialisieren alle Daten, die Sie werden hinzugefügt.

- Das Framework als Dokumente bereinigt, und schließen Sie die Ansichten. Sie müssen den Arbeitsspeicher freigeben, den Sie auf dem Heap aus den Memberfunktionen von diesen Dokumenten und Ansichten zugeordnet.

> [!NOTE]
>  Denken Sie daran, dass die Initialisierung für die gesamte Anwendung am besten in der Ihre Überschreibung erfolgt die [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Memberfunktion der Klasse `CWinApp`, und die Bereinigung für die gesamte Anwendung erfolgt am besten in Ihre Überschreibung der `CWinApp`Memberfunktion [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).

Der Lebenszyklus eines Dokuments (und dessen Rahmenfenster und anzeigen oder Sichten) in einer MDI-ist die Anwendung wie folgt:

1. Während der dynamischen Erstellung wird der Dokumentkonstruktor aufgerufen.

1. Für jedes neuen Dokuments, das Dokument des [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) oder [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) aufgerufen wird.

1. Der Benutzer interagiert mit dem Dokument während ihrer Lebensdauer. Dies geschieht in der Regel während der Benutzer auf Daten des Dokuments über die Ansicht arbeitet, auswählen und bearbeiten die Daten. Die Ansicht übergibt die Änderungen an das Dokument zur Speicherung und Aktualisierung von anderen Ansichten. Während dieser Zeit möglicherweise sowohl das Dokument als auch der Sicht, die Befehle behandeln.

1. Das Framework ruft [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) zum Löschen von Daten, die spezifisch für ein Dokument.

1. Der Destruktor des Dokuments wird aufgerufen.

Schritt 1 wird in einer SDI-Anwendung ausgeführt, einmal auf, wenn das Dokument zuerst erstellt wird. Klicken Sie dann werden die Schritte 2 bis 4 wiederholt jedes Mal ausgeführt, ein neues Dokument geöffnet ist. Das neue Dokument verwendet das vorhandene Document-Objekt. Schritt 5 wird schließlich ausgeführt, wenn die Anwendung beendet.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Initialisieren von Dokumenten und Ansichten](../mfc/initializing-documents-and-views.md)

- [Bereinigen von Dokumenten und Ansichten](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)
