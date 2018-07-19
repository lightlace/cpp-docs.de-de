---
title: Einstellen des Tagesstatus eines Monats Monatskalender-Steuerelement | Microsoft Docs
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
ms.openlocfilehash: 6d4254448e3f8f5a23acd9a303788fd13afb2f84
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950794"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Einstellen des Tagesstatus für ein Monatskalender-Steuerelement
Eines der Attribute für ein Monatskalender-Steuerelement ist die Fähigkeit zum Speichern von Informationen, die für jeden Tag des Monats als tagesstatus des Steuerelements bezeichnet. Diese Informationen werden verwendet, um bestimmte Datumsangaben für den Monat, der aktuell angezeigten hervorzuheben.  
  
> [!NOTE]
>  Die `CMonthCalCtrl` Objekt muss den MCS_DAYSTATE-Stil zum Anzeigen von Statusinformationen Tag aufweisen.  
  
 Zustandsinformationen Tag wird als 32-Bit-Datentyp, ausgedrückt **MONTHDAYSTATE**. Jedes bit in einem **MONTHDAYSTATE** Bitfeld (1 bis 31) stellt den Zustand für einen Tag eines Monats dar. Wenn eine Bit aktiviert ist, wird das entsprechende Tag angezeigt werden fett; Andernfalls wird es mit keine Hervorhebung angezeigt werden.  
  
 Es gibt zwei Methoden zum Festlegen des im Monatskalender-Steuerelement tagesstatus: explizit mit einem Aufruf von [CMonthCalCtrl:: SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) oder durch Behandeln der MCN_GETDAYSTATE-Benachrichtigung.  
  
## <a name="handling-the-mcngetdaystate-notification-message"></a>Behandeln der MCN_GETDAYSTATE-Benachrichtigung  
 Die MCN_GETDAYSTATE-Nachricht wird vom Steuerelement gesendet, um zu bestimmen, wie die Tage der sichtbaren Monate angezeigt werden soll.  
  
> [!NOTE]
>  Daran, dass das Steuerelement der vorherigen und folgenden Monate, in Bezug auf den sichtbaren Monat zwischenspeichert erhalten Sie diese Benachrichtigung jedes Mal, wenn ein neuer Monat ausgewählt ist.  
  
 Um diese Nachricht ordnungsgemäß behandeln zu können, müssen Sie feststellen, wie viele Monate Tageszustandsinformationen wird für angefordert wird, Initialisieren eines Arrays von **MONTHDAYSTATE** Strukturen mit den richtigen Werten und Initialisieren der zugehörigen Strukturmember mit den neuen Informationen. Das folgende Verfahren, die über die notwendigen Schritte wird vorausgesetzt, dass Sie eine `CMonthCalCtrl` bezeichnetes Objekt *M_monthcal* und ein Array von **MONTHDAYSTATE** Objekte *MdState*.  
  
#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>Behandeln der MCN_GETDAYSTATE-Benachrichtigung  
  
1.  Mithilfe des Eigenschaftenfensters hinzufügehandlers eine Benachrichtigung für die MCN_GETDAYSTATE-Nachricht an die *M_monthcal* Objekt (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).  
  
2.  Fügen Sie im Hauptteil der Handler den folgenden Code hinzu:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     Das Beispiel konvertiert die *pNMHDR* Zeiger auf den richtigen Typ bestimmt dann, wie viele Monate Informationen angefordert werden (`pDayState->cDayState`). Für jeden Monat, den aktuellen Bitfeld (`pDayState->prgDayState[i]`) wird mit 0 (null), und klicken Sie dann die erforderliche initialisiert werden (in diesem Fall dem 15. jedes Monats) festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

