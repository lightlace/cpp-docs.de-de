---
title: Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: e93e91a3219f81bf4027549fc84f1c85c8defb5b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507871"
---
# <a name="processing-notification-messages-in-list-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen

Wenn Benutzer auf Spaltenüberschriften klicken, Symbole ziehen, Bezeichnungen bearbeiten usw., sendet das Listen Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) Benachrichtigungs Meldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer beispielsweise auf einen Spaltenheader klickt, empfiehlt es sich, die Elemente basierend auf dem Inhalt der Spalte, auf die geklickt wurde, zu sortieren, wie in Microsoft Outlook.

Verarbeiten von WM_NOTIFY-Nachrichten aus dem Listen Steuerelement in der Ansicht oder der Dialogfeld Klasse. Verwenden Sie die Eigenschaftenfenster, um eine [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) -Handlerfunktion mit einer Switch-Anweisung zu erstellen, die darauf basiert, welche Benachrichtigungs Meldung verarbeitet wird.

Eine Liste der Benachrichtigungen, die ein Listen Steuerelement an sein übergeordnetes Fenster senden kann, finden Sie unter [Listenansicht-Steuerelement Verweis](/windows/win32/Controls/list-view-control-reference) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
