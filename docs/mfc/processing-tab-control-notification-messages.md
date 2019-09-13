---
title: Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: cc322a038717d48f440df1ec571674cec80743ce
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908060"
---
# <a name="processing-tab-control-notification-messages"></a>Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements

Wenn Benutzer auf Tabstopps oder Schaltflächen klicken, sendet das Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) Benachrichtigungs Meldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer beispielsweise auf eine Registerkarte klickt, empfiehlt es sich, die Steuerelement Daten vor der Anzeige auf der Seite vorzulegen.

Verarbeiten von WM_NOTIFY-Nachrichten aus dem Registerkarten-Steuerelement in der Ansicht oder Dialogfeld Klasse Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um eine [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) -Handlerfunktion mit einer Switch-Anweisung zu erstellen, die darauf basiert, welche Benachrichtigung verarbeitet wird. Eine Liste der Benachrichtigungen, die ein Registerkarten-Steuerelement an das übergeordnete Fenster senden kann, finden Sie im Abschnitt " **Benachrichtigungen** " unter Registerkarten- [Steuerelement Verweis](/windows/win32/controls/tab-control-reference) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
