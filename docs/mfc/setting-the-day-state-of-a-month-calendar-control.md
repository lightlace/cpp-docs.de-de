---
title: Einstellen des Tagesstatus für ein Monatskalender-Steuerelement
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: b8a91c8b0c3bdef9256628b9226c5f3ff154ed7d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907526"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Einstellen des Tagesstatus für ein Monatskalender-Steuerelement

Eines der Attribute eines Monatskalender-Steuer Elements ist die Möglichkeit, Informationen, die für jeden Tag des Monats als Tageszustand des Steuer Elements bezeichnet werden, zu speichern. Diese Informationen werden verwendet, um bestimmte Datumsangaben für den aktuell angezeigten Monat hervorzuheben.

> [!NOTE]
>  Das `CMonthCalCtrl` Objekt muss den MCS_DAYSTATE-Stil aufweisen, um die Tages Zustandsinformationen anzuzeigen.

Die Tages Zustandsinformationen werden als 32-Bit-Datentyp **MONTHDAYSTATE**ausgedrückt. Jedes Bit in einem **MONTHDAYSTATE** -Bitfeld (1 bis 31) stellt den Status eines Tags in einem Monat dar. Wenn ein Bit ist, wird der entsprechende Tag fett angezeigt. Andernfalls wird Sie ohne Betonung angezeigt.

Es gibt zwei Methoden, um den Tageszustand des Monatskalender-Steuer Elements festzulegen: explizit mit einem [CMonthCalCtrl:: SetDayState-CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md#setdaystate) -Befehl oder mit der MCN_GETDAYSTATE-Benachrichtigungs Meldung.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>Verarbeiten der MCN_GETDAYSTATE-Benachrichtigungs Meldung

Die MCN_GETDAYSTATE-Nachricht wird vom-Steuerelement gesendet, um zu bestimmen, wie die Tage innerhalb der sichtbaren Monate angezeigt werden sollen.

> [!NOTE]
>  Da das Steuerelement die vorherigen und die folgenden Monate in Bezug auf den sichtbaren Monat zwischenspeichert, erhalten Sie diese Benachrichtigung jedes Mal, wenn ein neuer Monat ausgewählt wird.

Um diese Nachricht ordnungsgemäß zu verarbeiten, müssen Sie bestimmen, für wie viele Monate Zustandsinformationen angefordert werden, ein Array von **MONTHDAYSTATE** -Strukturen mit den richtigen Werten initialisieren und den zugehörigen Strukturmember mit dem neuen initialisieren. Informationen. In der folgenden Prozedur, in der die erforderlichen Schritte erläutert werden, wird `CMonthCalCtrl` davon ausgegangen, dass Sie ein-Objekt namens *m_monthcal* und ein Array von **MONTHDAYSTATE** -Objekten, *mdState*, besitzen.

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>So verarbeiten Sie die MCN_GETDAYSTATE-Benachrichtigungs Meldung

1. Fügen Sie dem *m_monthcal* -Objekt mithilfe des [Klassen-Assistenten](reference/mfc-class-wizard.md)einen Benachrichtigungs Handler für die MCN_GETDAYSTATE-Nachricht hinzu (siehe [Mapping von Nachrichten zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. Fügen Sie im Text des Handlers den folgenden Code hinzu:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   Im Beispiel wird der *pNMHDR* -Zeiger in den richtigen Typ konvertiert und dann bestimmt, wie viele Monate Informationen angefordert werden`pDayState->cDayState`(). Für jeden Monat wird das aktuelle Bitfeld (`pDayState->prgDayState[i]`) mit 0 (null) initialisiert, und anschließend werden die benötigten Datumsangaben festgelegt (in diesem Fall der 15. jedes Monats).

## <a name="see-also"></a>Siehe auch

[Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
