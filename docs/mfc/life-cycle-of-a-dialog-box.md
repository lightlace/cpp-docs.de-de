---
title: Arbeiten mit Dialog Feldern in MFC
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: ad15250cf9a8dd663072cf9423263260bbb40a0e
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685730"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>Arbeiten mit Dialog Feldern in MFC

Während des Lebenszyklus eines Dialog Felds ruft der Benutzer das Dialogfeld auf, in der Regel innerhalb eines Befehls Handlers, der das Dialogfeld Objekt erstellt und initialisiert, der Benutzer mit dem Dialogfeld interagiert und dann das Dialogfeld geschlossen wird.

Für modale Dialogfelder sammelt der Handler alle Daten, die der Benutzer eingegeben hat, nachdem das Dialogfeld geschlossen wurde. Da das Dialogfeld Objekt vorhanden ist, nachdem das Dialogfeld geschlossen wurde, können Sie die Daten einfach mithilfe der Element Variablen der Dialogfeld Klasse extrahieren.

Bei nicht modalem Dialogfeldern können Sie häufig Daten aus dem Dialogfeld Objekt extrahieren, während das Dialogfeld noch sichtbar ist. An einem bestimmten Punkt wird das Dialog Objekt zerstört. Wenn dies der Fall ist, hängt von Ihrem Code ab.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Erstellen und Anzeigen von Dialogfeldern](../mfc/creating-and-displaying-dialog-boxes.md)

- [Erstellen von modalen Dialogfeldern](../mfc/creating-modal-dialog-boxes.md)

- [Erstellen von nicht modalem Dialogfeldern](../mfc/creating-modeless-dialog-boxes.md)

- [Verwenden einer Dialogfeld Vorlage im Speicher](../mfc/using-a-dialog-template-in-memory.md)

- [Festlegen der Hintergrundfarbe für das Dialogfeld](../mfc/setting-the-dialog-boxs-background-color.md)

- [Initialisieren des Dialog Felds](../mfc/initializing-the-dialog-box.md)

- [Verarbeiten von Windows-Meldungen in Ihrem Dialogfeld](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [Abrufen von Daten aus dem Dialogfeld Objekt](../mfc/retrieving-data-from-the-dialog-object.md)

- [Schließen des Dialog Felds](../mfc/closing-the-dialog-box.md)

- [Zerstören des Dialog Felds](../mfc/destroying-the-dialog-box.md)

- [Dialog Datenaustausch (DDX) und Validierung (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Dialogfelder für Eigenschaften Blätter](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)
