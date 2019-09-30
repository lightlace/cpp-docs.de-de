---
title: Zuordnen von Windows-Meldungen zu einer Klasse
ms.date: 09/06/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
- Class Wizard [MFC]
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 0f1207faca56acd709db86478722eba85eeb284a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685614"
---
# <a name="mapping-windows-messages-to-your-class"></a>Zuordnen von Windows-Meldungen zu einer Klasse

Wenn Sie das Dialogfeld zum Verarbeiten von Windows-Meldungen benötigen, überschreiben Sie die entsprechenden Handlerfunktionen. Wählen Sie hierzu in **Projektmappen-Explorer**die Registerkarte **Klassenansicht** aus, klicken Sie mit der rechten Maustaste auf die Klasse, die das Dialogfeld darstellt, und wählen Sie [Klassen-Assistent](reference/mfc-class-wizard.md)aus. Verwenden Sie den Assistenten, um [die Nachrichten](../mfc/reference/mapping-messages-to-functions.md) der Dialogfeld Klasse zuzuordnen. Dadurch wird ein Meldungs Zuordnungs Eintrag für jede Nachricht geschrieben, und die Member der nachrichtenhandlermember werden der Klasse hinzugefügt. Verwenden Sie den Code-Editor, um Code in den Meldungs Handlern zu schreiben.

Sie können auch Member-Funktionen von [CDialog](../mfc/reference/cdialog-class.md) und deren Basisklassen überschreiben, insbesondere [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Nachrichten Behandlung und-Zuordnung](../mfc/message-handling-and-mapping.md)

- [Häufig überschriebene Element Funktionen](../mfc/commonly-overridden-member-functions.md)

- [Häufig hinzugefügte Member-Funktionen](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
