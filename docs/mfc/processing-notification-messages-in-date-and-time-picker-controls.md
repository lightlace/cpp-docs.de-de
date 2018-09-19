---
title: Verarbeiten von Nachrichten in arithmetischen Datums- und Zeitauswahl Steuerelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs:
- C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ae7773d46d93f0f2c5a237f833da4c81679084c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414380"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen für Zeit und Datum

Da Benutzer mit das Datum und Uhrzeit Datumsauswahl-Steuerelement, das Steuerelement interagieren (`CDateTimeCtrl`) sendet benachrichtigungsmeldungen an das übergeordnete Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt-Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer die Datums- / Zeitauswahl anzuzeigende das eingebettete Monatskalender-Steuerelement geöffnet wird, wird z. B. die DTN_DROPDOWN-Benachrichtigung gesendet.

Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

Die folgende Liste beschreibt die verschiedenen Benachrichtigungen, die von den Datums- / Zeitauswahl-Steuerelement gesendet werden.

- DTN_DROPDOWN benachrichtigt ist das übergeordnete Element, das das eingebettete Monatskalender-Steuerelement angezeigt wird. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde. Weitere Informationen über diese Benachrichtigung finden Sie unter [den Zugriff auf das eingebettete Monatskalender-Steuerelement](../mfc/accessing-the-embedded-month-calendar-control.md).

- DTN_CLOSEUP benachrichtigt wird das übergeordnete Element, das das eingebettete Monatskalender-Steuerelement geschlossen werden. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde.

- DTN_DATETIMECHANGE Benachrichtigt das übergeordnete Element, das im Steuerelement eine Änderung vorgenommen wurde.

- Erforderlich, DTN_FORMAT benachrichtigt das übergeordnete Element, das Text, der im Rückruffeld angezeigt werden. Weitere Informationen über diese Benachrichtigung und Rückruffeldern finden Sie unter [Verwenden von Rückruffeldern in einem Datums- und Zeitauswahl-Steuerelement](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_FORMATQUERY Fordert das übergeordnete Element, das die maximale zulässige Größe der Zeichenfolge angeben, der im Rückruffeld angezeigt wird. Behandeln diese Benachrichtigung kann das Steuerelement ordnungsgemäß Anzeigeausgabe jederzeit aktiv, vermindern des Flackerns in der Anzeige des Steuerelements. Weitere Informationen über diese Benachrichtigung finden Sie unter [Verwenden von Rückruffeldern in einem Datums- und Zeitauswahl-Steuerelement](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

- DTN_USERSTRING Benachrichtigt das übergeordnete Element, das Bearbeiten des Inhalts der Datums- / Zeitauswahl-Steuerelement beendet ist. Diese Benachrichtigung wird nur gesendet, wenn der Stil DTS_APPCANPARSE festgelegt wurde.

- DTN_WMKEYDOWN benachrichtigt das übergeordnete Element aus, wenn der Benutzer im Rückruffeld eingibt. Behandeln Sie diese Benachrichtigung, um die für nicht-Rückruffeldern in einem Datums- / Zeitauswahl-Steuerelement unterstützt Tastaturantworten zu emulieren. Weitere Informationen über diese Benachrichtigung finden Sie unter [Unterstützung von Rückruffeldern in einem DTP-Steuerelement](/windows/desktop/Controls/date-and-time-picker-controls) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

