---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51fff5b7e43b489bdaf2a27b115af26c48e33956
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400788"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement

Vordefinierte Ereignisse unterscheiden sich von benutzerdefinierten Ereignissen, da sie automatisch von-Klasse ausgelöst wurden [COleControl](../mfc/reference/colecontrol-class.md). `COleControl` enthält vordefinierte Memberfunktionen, die Ereignisse, die durch häufige Aktionen ausgelöst werden. Einige häufig verwendete Aktionen, die von implementiert `COleControl` enthalten einzelne - und double - clicks auf das Steuerelement Tastaturereignisse und Änderungen in den Zustand der Maustasten. Ereignis map-Eingaben für vordefinierte Ereignisse immer die EVENT_STOCK-Präfix vorangestellt sind.

##  <a name="_core_stock_events_supported_by_classwizard"></a> Vordefinierte Ereignisse, die von unterstützt die Ereignis-Assistent zum Hinzufügen von

Die `COleControl` Klasse enthält zehn vordefinierte Ereignisse, die in der folgenden Tabelle aufgeführt. Sie können angeben, die Ereignisse in Ihrem Steuerelement mithilfe der [Assistenten zum Hinzufügen von Ereignis](../ide/add-event-wizard.md).

### <a name="stock-events"></a>Bestandereignissen

|event|Auslösen der Funktion|Kommentare|
|-----------|---------------------|--------------|
|Klicken|**"void" FireClick)**|Wird ausgelöst, wenn das Steuerelement die Mausauswahl, alle erhält **BUTTONUP** (linke, mittlere oder Rechte) Nachricht empfangen wird und die Maustaste losgelassen wird, über dem Steuerelement. Die Lagerbestände MouseDown und das MouseUp-Ereignisse auftreten, bevor Sie dieses Ereignis.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_CLICK)**|
|DblClick|**"void" FireDblClick)**|Ähnlich wie auf jedoch ausgelöst, wenn eine **BUTTONDBLCLK** Nachricht empfangen wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_DBLCLICK)**|
|Fehler|**"void" FireError (SCODE**  *Scode*  **, LPCSTR** `lpszDescription` **, "uint"**`nHelpID`**= 0)**|Ausgelöst, wenn Sie in das ActiveX-Steuerelement außerhalb des Bereichs eine Methode aufrufen oder Eigenschaftszugriff ein Fehler auftritt.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_ERROREVENT)**|
|KeyDown|**"void" FireKeyDown (kurze** `nChar` **, short**  `nShiftState`  **)**|Wird ausgelöst, wenn eine `WM_SYSKEYDOWN` oder `WM_KEYDOWN` Nachricht empfangen wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_KEYDOWN)**|
|KeyPress|**"void" FireKeyPress (kurze** <strong>\*</strong> `pnChar` **)** |Wird ausgelöst, wenn eine `WM_CHAR` Nachricht empfangen wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_KEYPRESS)**|
|KeyUp|**"void" FireKeyUp (kurze** `nChar` **, short**`nShiftState`**)** |Wird ausgelöst, wenn eine `WM_SYSKEYUP` oder `WM_KEYUP` Nachricht empfangen wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_KEYUP)**|
|MouseDown|**"void" FireMouseDown (kurze**  `nButton`  **, short**  `nShiftState` **, "float"**  *x*  **, "float"**  *y*  **)**|Wird ausgelöst, wenn alle **BUTTONDOWN** (links, mittleren oder rechten) empfangen wird. Die Mauseingabe wird unmittelbar vor diesem Ereignis ausgelöst wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_MOUSEDOWN)**|
|MouseMove|**"void" FireMouseMove (kurze**  `nButton`  **, short**  `nShiftState` **, "float"**  *x*  **, "float"**  *y*  **)**|Wird ausgelöst, wenn eine WM_MOUSEMOVE-Meldung empfangen wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_MOUSEMOVE)**|
|MouseUp|**"void" FireMouseUp (kurze**  `nButton`  **, short**  `nShiftState`  **, "float"**  *x*  **, "float"**  *y*  **)**|Wird ausgelöst, wenn alle **BUTTONUP** (links, mittleren oder rechten) empfangen wird. Das Erfassen von Mauseingaben wird freigegeben, bevor dieses Ereignis ausgelöst wird.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_MOUSEUP)**|
|ReadyStateChange|**"void" FireReadyStateChange)**|Wird ausgelöst, wenn der Übergang eines Steuerelements zum nächsten Zustand "bereit" aufgrund der Menge der empfangenen Daten.<br /><br /> Ereignis-Zuordnungseintrag: **EVENT_STOCK_READYSTATECHANGE)**|

##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Hinzufügen eines Ereignis mit der Ereignis-Assistent zum Hinzufügen von

Hinzufügen von vordefinierten Ereignissen erfordert weniger Arbeit dar als das Hinzufügen von benutzerdefinierten Ereignissen, da das Auslösen des tatsächlichen Ereignisses automatisch von der Basisklasse, erfolgt `COleControl`. Das folgende Verfahren ein Steuerelement, das mit entwickelt wurde ein Ereignis hinzugefügt [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md). Das Ereignis namens KeyPress-Ereignis wird ausgelöst, wenn eine Taste gedrückt wird und das Steuerelement aktiv ist. Dieses Verfahren kann auch verwendet werden, um andere vordefinierte Ereignisse hinzuzufügen. Ersetzen Sie den Namen der ausgewählten Ereignis auf Tastendruck.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Die vordefinierte KeyPress-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzufügen

1. Laden Sie das Steuerelementprojekt.

1. In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Ereignis hinzufügen**.

     Daraufhin den Assistenten zum Hinzufügen eines Ereignisses.

1. In der **Ereignisnamen** Dropdown-Liste `KeyPress`.

1. Klicken Sie auf **Fertig stellen**.

##  <a name="_core_classwizard_changes_for_stock_events"></a> Fügen Sie-Assistent ändert für vordefinierte Ereignisse hinzu.

Da vordefinierte Ereignisse von der Basisklasse des Steuerelements behandelt werden, den Assistenten zum Hinzufügen eines Ereignisses nicht Ihrer Klassendeklaration in keiner Weise geändert. Er fügt das Ereignis des Steuerelements Event-Zuordnung hinzu, und stellt einen Eintrag in der. IDL-Datei. Ereigniszuordnung des Steuerelements, befindet sich in der Implementierung des Steuerelements-Klasse die folgende Zeile hinzugefügt wird (. CPP)-Datei:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Ein KeyPress-Ereignis, wenn eine WM_CHAR-Meldung empfangen wird, und das Steuerelement aktiv ist, wird ausgelöst, wenn Sie diesen Code hinzufügen. Das KeyPress-Ereignis kann zu anderen Zeiten ausgelöst werden, durch den Aufruf der Funktion auslösen (z. B. `FireKeyPress`) aus dem Steuerelementcode.

Den Assistenten zum Hinzufügen von Ereignis hinzugefügt des Steuerelements die folgende Codezeile. IDL-Datei:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Diese Zeile verknüpft das KeyPress-Ereignis mit der standardmäßigen Dispatch-ID und der Container kann das KeyPress-Ereignis zu erwarten.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)
