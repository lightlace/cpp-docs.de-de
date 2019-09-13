---
title: Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 92111e3e0a4869ca06b89d2d18d38aab9f10ab7d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908091"
---
# <a name="processing-notification-messages-in-list-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen

Wenn Benutzer auf Spaltenüberschriften klicken, Symbole ziehen, Bezeichnungen bearbeiten usw., sendet das Listen Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) Benachrichtigungs Meldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer beispielsweise auf einen Spaltenheader klickt, empfiehlt es sich, die Elemente basierend auf dem Inhalt der Spalte, auf die geklickt wurde, zu sortieren, wie in Microsoft Outlook.

Verarbeiten von WM_NOTIFY-Nachrichten aus dem Listen Steuerelement in der Ansicht oder der Dialogfeld Klasse. Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um eine [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) -Handlerfunktion mit einer Switch-Anweisung zu erstellen, die darauf basiert, welche Benachrichtigung verarbeitet wird.

Eine Liste der Benachrichtigungen, die ein Listen Steuerelement an sein übergeordnetes Fenster senden kann, finden Sie unter [Listenansicht-Steuerelement Verweis](/windows/win32/Controls/list-view-control-reference) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
