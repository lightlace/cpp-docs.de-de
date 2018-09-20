---
title: Zugreifen auf das eingebettete Monatskalender-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a92660223c84c5f53bc848e72b03316602180d36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430292"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Zugreifen auf das eingebettete Monatskalender-Steuerelement

Das eingebettete Monatskalender-Steuerelement Kalenderobjekt aus zugegriffen werden kann die `CDateTimeCtrl` Objekt durch einen Aufruf der [Memberfunktion GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) Member-Funktion.

> [!NOTE]
>  Das eingebettete Monatskalender-Steuerelement wird nur verwendet, wenn die Datums- / Zeitauswahl-Steuerelement keinen der **DTS_UPDOWN** Satz formatieren.

Dies ist nützlich, wenn bestimmte Attribute zu ändern, bevor das integrierte Steuerelement angezeigt werden sollen. Zu diesem Zweck behandeln die **DTN_DROPDOWN** Benachrichtigung Abrufen des Monatskalender-Steuerelements (mit [CDateTimeCtrl:: GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)), und nehmen Sie Ihre Änderungen vor. Leider ist im Monatskalender-Steuerelement nicht persistent.

Das heißt, wenn der Benutzer die Anzeige der im Monatskalender-Steuerelement angefordert wird, ein neues Monatskalender-Steuerelement wird erstellt (vor der **DTN_DROPDOWN** Benachrichtigung). Das Steuerelement gelöscht wird (nachdem die **DTN_CLOSEUP** Notification) als vom Benutzer verworfen. Dies bedeutet, dass alle Attribute, die Sie ändern, bevor das integrierte Steuerelement angezeigt wird, die verloren gegangen sind, wenn das integrierte Steuerelement geschlossen wird.

Das folgende Beispiel veranschaulicht dieses Verfahren unter Verwendung eines Handlers für die **DTN_DROPDOWN** Benachrichtigung. Der Code ändert die Hintergrundfarbe der im Monatskalender-Steuerelement, mit einem Aufruf von [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), grau dargestellt. Der Code lautet wie folgt aus:

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Wie bereits erwähnt, sind alle Änderungen an Eigenschaften, der im Monatskalender-Steuerelement verloren geht, mit zwei Ausnahmen angezeigt, wenn das integrierte Steuerelement geschlossen wird. Die erste Ausnahme, die Farben der im Monatskalender-Steuerelement, wurde bereits besprochen. Die zweite Ausnahme ist die Schriftart, die von der im Monatskalender-Steuerelement verwendet. Sie können die Standardschriftart ändern, indem Sie einen Aufruf an [CDateTimeCtrl:: SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), übergeben das Handle für eine vorhandene Schriftart. Im folgenden Beispiel (wo `m_dtPicker` ist das Datum und Uhrzeit-Steuerelementobjekt) veranschaulicht eine mögliche Methode:

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

Nachdem die Schriftart, mit einem Aufruf von geändert wurde `CDateTimeCtrl::SetMonthCalFont`, die neue Schriftart gespeichert und verwendet das nächste Mal werden, dass ein Monatskalender angezeigt werden soll.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

