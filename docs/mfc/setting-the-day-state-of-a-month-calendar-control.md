---
title: Einstellen des Tagesstatus für ein Monatskalender-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b443e1758f766b7fa2dd9a0169ab98172423779d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439341"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Einstellen des Tagesstatus für ein Monatskalender-Steuerelement

Eines der Attribute von einem Monatskalender-Steuerelement ist die Möglichkeit zum Speichern von Informationen, die als des tagesstatus für das Steuerelement, für jeden Tag des Monats bezeichnet. Diese Informationen werden verwendet, um bestimmte Datumsangaben für den derzeit angezeigten Monat hervorzuheben.

> [!NOTE]
>  Die `CMonthCalCtrl` Objekt muss den MCS_DAYSTATE-Stil zum Anzeigen von Statusinformationen für Tag aufweisen.

Zustandsinformationen Tag wird als 32-Bit-Datentyp, ausgedrückt **MONTHDAYSTATE**. Jedes bit in einem **MONTHDAYSTATE** Bitfeld (1 bis 31) stellt den Zustand eines Tages in einem Monat dar. Wenn eine Bit aktiviert ist, wird der entsprechenden Tag angezeigt werden fett; Andernfalls wird es mit keine Hervorhebung angezeigt.

Es gibt zwei Methoden zum Einstellen des tagesstatus, der im Monatskalender-Steuerelement: explizit mit einem Aufruf von [CMonthCalCtrl:: SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) oder durch Behandeln der MCN_GETDAYSTATE-Benachrichtigung.

## <a name="handling-the-mcngetdaystate-notification-message"></a>Behandeln der MCN_GETDAYSTATE-Benachrichtigung

Die MCN_GETDAYSTATE-Nachricht wird vom Steuerelement gesendet, um zu bestimmen, wie die Tage der sichtbaren Monate angezeigt werden soll.

> [!NOTE]
>  Da das Steuerelement die vorherigen und folgenden Monaten in Bezug auf den sichtbaren Monat zwischenspeichert erhalten Sie diese Benachrichtigung jedes Mal, wenn ein neuer Monat ausgewählt ist.

Um diese Nachricht richtig behandeln zu können, müssen Sie bestimmen, wie viele Monate Tageszustandsinformationen wird für angefordert wird, Initialisieren eines Arrays von **MONTHDAYSTATE** Strukturen mit der richtigen Werte, und Initialisieren der zugehörigen Strukturmember mit den neuen Informationen. Das folgende Verfahren, mit Details zu die erforderlichen Schritten wird vorausgesetzt, dass Sie eine `CMonthCalCtrl` Objekt mit dem Namen *M_monthcal* und ein Array von **MONTHDAYSTATE** Objekte *MdState*.

#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>Um die MCN_GETDAYSTATE-Benachrichtigung zu verarbeiten.

1. Das Fenster "Eigenschaften", hinzufügen einen Benachrichtigungshandler für die MCN_GETDAYSTATE-Nachricht an die *M_monthcal* Objekt (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. Fügen Sie im Text des Handlers den folgenden Code hinzu:

     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

     Im Beispiel wird die *pNMHDR* Zeiger auf den richtigen Typ, dann bestimmt, wie viele Monate Informationen angefordert werden (`pDayState->cDayState`). Für jeden Monat, den aktuellen Bitfeld (`pDayState->prgDayState[i]`) wird mit 0 (null), und klicken Sie dann die erforderliche initialisiert Datumsangaben (in diesem Fall dem 15. jedes Monats) festgelegt sind.

## <a name="see-also"></a>Siehe auch

[Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

