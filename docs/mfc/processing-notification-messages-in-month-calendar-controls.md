---
title: Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bbdb3728009cdee978bb08ef8df8817f1ef5e41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378175"
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

