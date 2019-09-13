---
title: Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 452d24bf1ffd157366f357a510e8c8cfaad28d91
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908083"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen

Wenn Benutzer mit dem month Calendar-Steuerelement interagieren (Datumsangaben auswählen und/oder einen anderen Monat anzeigen),`CMonthCalCtrl`sendet das Steuerelement () Benachrichtigungs Meldungen an das übergeordnete Fenster, in der Regel eine Ansicht oder ein Dialog Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer z. b. einen neuen Monat zum anzeigen auswählt, können Sie einen Satz von Datumsangaben angeben, der hervorgehoben werden soll.

Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um der übergeordneten Klasse Benachrichtigungs Handler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

In der folgenden Liste werden die verschiedenen Benachrichtigungen beschrieben, die vom Monatskalender-Steuerelement gesendet werden.

- MCN_GETDAYSTATE fordert Informationen darüber an, welche Tage fett angezeigt werden sollen. Informationen zur Behandlung dieser Benachrichtigung finden Sie unter [Festlegen des Tages Zustands eines Monatskalender-Steuer](../mfc/setting-the-day-state-of-a-month-calendar-control.md)Elements.

- MCN_SELCHANGE benachrichtigt das übergeordnete Element, dass sich das ausgewählte Datum oder der ausgewählte Bereich des Datums geändert hat.

- MCN_SELECT benachrichtigt das übergeordnete Element, dass eine explizite Datumsauswahl erfolgt ist.

## <a name="see-also"></a>Siehe auch

[Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
