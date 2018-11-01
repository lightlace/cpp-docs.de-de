---
title: Zuordnen von Windows-Meldungen zu einer Klasse
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 37c0f61f4d38e3e152d9dd508c9487782ebdf81a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630459"
---
# <a name="mapping-windows-messages-to-your-class"></a>Zuordnen von Windows-Meldungen zu einer Klasse

Bei Bedarf das Dialogfeld, um Windows-Meldungen zu verarbeiten, überschreiben Sie die entsprechenden Handler-Funktionen. Zu diesem Zweck verwenden Sie im Eigenschaftenfenster in [ordnen die Nachrichten](../mfc/reference/mapping-messages-to-functions.md) der Dialogfeld-Klasse. Schreibt einen meldungszuordnung Eintrag für jede Nachricht, und fügt die Meldungshandler-Memberfunktionen der Klasse hinzu. Verwenden Sie die Visual C++ Quellcode-Editor, um das Schreiben von Code in der Meldungshandler.

Sie können auch festlegen, überschreiben Memberfunktionen der [CDialog](../mfc/reference/cdialog-class.md) und deren Basisklassen, vor allem [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

- [Überschreibbare Memberfunktionen](../mfc/commonly-overridden-member-functions.md)

- [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

