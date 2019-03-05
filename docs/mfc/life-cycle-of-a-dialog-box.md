---
title: Lebenszyklus eines Dialogfelds
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: a3772a180e35a57c997446fcf2268d84bec2daa5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291105"
---
# <a name="life-cycle-of-a-dialog-box"></a>Lebenszyklus eines Dialogfelds

Während des Lebenszyklus eines Dialogfelds der Benutzer ruft das Dialogfeld, in der Regel in einem Befehlshandler, der erstellt und initialisiert das Dialogfeldobjekt, der Benutzer interagiert mit dem Dialogfeld und das Dialogfeld geschlossen wird.

Für modale Dialogfelder sammelt der Handler keine Daten vom Benutzer eingegeben wird, sobald das Dialogfeld geschlossen wird. Da das Dialogfeldobjekt vorhanden ist, nachdem das Dialogfeld-Fenster geschlossen wurde, können Sie einfach die Membervariablen der Dialogfeldklasse verwenden, um Daten zu extrahieren.

Nicht modale Dialogfelder möglicherweise häufig extrahieren Sie Daten aus dem Dialogfeldobjekt während das Dialogfeld immer noch sichtbar ist. An einem bestimmten Punkt wird das Dialogfeldobjekt zerstört. Wenn dies geschieht, hängt von Ihrem Code ab.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen und Anzeigen von Dialogfeldern](../mfc/creating-and-displaying-dialog-boxes.md)

- [Erstellen von modalen Dialogfeldern](../mfc/creating-modal-dialog-boxes.md)

- [Erstellen von nicht modalen Dialogfeldern](../mfc/creating-modeless-dialog-boxes.md)

- [Verwenden einer Dialogvorlage im Speicher](../mfc/using-a-dialog-template-in-memory.md)

- [Festlegen der Hintergrundfarbe des Dialogfelds](../mfc/setting-the-dialog-boxs-background-color.md)

- [Initialisieren des Dialogfelds](../mfc/initializing-the-dialog-box.md)

- [Verarbeiten von Windows-Meldungen in einem Dialogfeld](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [Abrufen von Daten aus dem Dialogfeldobjekt](../mfc/retrieving-data-from-the-dialog-object.md)

- [Schließen des Dialogfelds](../mfc/closing-the-dialog-box.md)

- [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md)

- [Dialogdatenaustausch (DDX) und Überprüfung (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Blatt Dialogfelder](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)
