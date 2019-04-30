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
ms.openlocfilehash: fc0bb475a95450c281c92b500083c9502df50931
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346147"
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
