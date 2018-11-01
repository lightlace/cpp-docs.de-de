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
ms.openlocfilehash: 3dbf50080bea59c4df4a9c92a135a65b093f7674
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511929"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen

Während Benutzer mit der im Monatskalender-Steuerelement (Auswahl von Datumsangaben und/oder einen anderen Monat anzeigen), das Steuerelement interagieren (`CMonthCalCtrl`) sendet benachrichtigungsmeldungen an das übergeordnete Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt-Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer an einen neuen Monat auswählt, können Sie beispielsweise einen Satz mit Datumsangaben bereitstellen, die hervorgehoben werden soll.

Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

Die folgende Liste beschreibt die verschiedenen Benachrichtigungen, die von der im Monatskalender-Steuerelement gesendet werden.

- MCN_GETDAYSTATE fordert Informationen darüber, welche Tage in Fettschrift angezeigt werden sollen. Weitere Informationen zur Behandlung dieser Benachrichtigung finden Sie unter [Einstellen des Tagesstatus für ein Monatskalender-Steuerelement](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- MCN_SELCHANGE benachrichtigt das übergeordnete Element, das das ausgewählte Datum oder der Datumsbereich geändert wurde.

- MCN_SELECT benachrichtigt das übergeordnete Element, das eine explizites Datumsauswahl getroffen wurde.

## <a name="see-also"></a>Siehe auch

[Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

