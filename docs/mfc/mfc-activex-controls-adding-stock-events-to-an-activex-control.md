---
title: "MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99de785bba9f566c5dbb4751f788320b96782427
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement
Vordefinierte Ereignisse unterscheiden sich von benutzerdefinierten Ereignissen, insofern, dass sie automatisch von-Klasse ausgelöst wurden [COleControl](../mfc/reference/colecontrol-class.md). `COleControl`enthält vordefinierte Memberfunktionen, die häufig verwendete Aktionen infolge Ereignisse ausgelöst werden. Einige häufig verwendete Aktionen von implementiert `COleControl` enthalten einzelne - und double - clicks auf das Steuerelement, Tastaturereignisse und Änderungen in den Zustand der Maustasten. Ereignis-Zuordnungseinträge für vordefinierte Ereignisse immer vorangestellt werden die **EVENT_STOCK** Präfix.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a>Vordefinierte Ereignisse, die von unterstützt die Ereignis-Assistent zum Hinzufügen von  
 Die `COleControl` Klasse enthält zehn vordefinierte Ereignisse, die in der folgenden Tabelle aufgeführt. Sie können angeben, dass die Ereignisse in Ihrer Steuerelement mit der [Assistenten zum Hinzufügen von Ereignis](../ide/add-event-wizard.md).  
  
### <a name="stock-events"></a>Bestandereignissen  
  
|event|Auslösende Funktion|Kommentare|  
|-----------|---------------------|--------------|  
|Klicken|**"void" FireClick)**|Wird ausgelöst, wenn das Steuerelement die Maus erfasst, die alle **BUTTONUP** (linke, mittlere oder Rechte) Nachricht empfangen wird, und die Maustaste losgelassen wird über dem Steuerelement. Die Stock MouseDown und MouseUp-Ereignisse auftreten, bevor Sie dieses Ereignis.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_CLICK)**|  
|DblClick|**"void" FireDblClick)**|Ähnlich wie auf jedoch ausgelöst wird, wenn eine **BUTTONDBLCLK** Nachricht empfangen wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_DBLCLICK)**|  
|Fehler|**"void" FireError (SCODE***Scode* **, LPCSTR** `lpszDescription` **, "uint"**`nHelpID`**= 0)** |Wird ausgelöst, wenn in das ActiveX-Steuerelement außerhalb des Gültigkeitsbereichs des Methodenzugriff Aufruf oder eine Eigenschaft ein Fehler auftritt.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_ERROREVENT)**|  
|KeyDown|**"void" FireKeyDown (kurze** `nChar` **, short**`nShiftState`**)** |Wird ausgelöst, wenn eine `WM_SYSKEYDOWN` oder `WM_KEYDOWN` Nachricht empfangen wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_KEYDOWN)**|  
|KeyPress|**"void" FireKeyPress (kurze\***`pnChar`**)** |Wird ausgelöst, wenn eine `WM_CHAR` Nachricht empfangen wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_KEYPRESS)**|  
|KeyUp|**"void" FireKeyUp (kurze** `nChar` **, short**`nShiftState`**)** |Wird ausgelöst, wenn eine `WM_SYSKEYUP` oder `WM_KEYUP` Nachricht empfangen wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_KEYUP)**|  
|MouseDown|**"void" FireMouseDown (kurze** `nButton` **, short** `nShiftState` **, "float"***x* **, "float"** *y***)** |Wird ausgelöst, wenn alle **BUTTONDOWN** (links, zentriert oder rechts) empfangen wird. Unmittelbar vor dem Ausführen dieses Ereignis ausgelöst wird, wird die Maus erfasst.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_MOUSEDOWN)**|  
|MouseMove|**"void" FireMouseMove (kurze** `nButton` **, short** `nShiftState` **, "float"***x* **, "float"** *y***)** |Wird ausgelöst, wenn eine `WM_MOUSEMOVE` Nachricht empfangen wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_MOUSEMOVE)**|  
|MouseUp|**"void" FireMouseUp (kurze** `nButton` **, short** `nShiftState` **, "float"***x* **, "float"** *y***)** |Wird ausgelöst, wenn alle **BUTTONUP** (links, zentriert oder rechts) empfangen wird. Das Erfassen von Mauseingaben wird freigegeben, bevor Sie dieses Ereignis ausgelöst wird.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_MOUSEUP)**|  
|ReadyStateChange|**"void" FireReadyStateChange)**|Wird ausgelöst, wenn der Übergang eines Steuerelement zum nächsten Zustand "bereit" aufgrund des Umfangs der Daten empfangen wurde.<br /><br /> Eintrag für die Zuordnung: **EVENT_STOCK_READYSTATECHANGE)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a>Hinzufügen eines vordefinierten Ereignisses mit der Ereignis-Assistent zum Hinzufügen von  
 Hinzufügen von vordefinierten Ereignissen erfordert weniger aufwendig als das Hinzufügen von benutzerdefinierten Ereignissen, da das Auslösen des tatsächlichen Ereignisses automatisch von der Basisklasse behandelt wird `COleControl`. Das folgende Verfahren fügt ein vordefiniertes Ereignis an ein Steuerelement, das entwickelt wurde mit [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md). Das Ereignis wird aufgerufen, KeyPress wird ausgelöst, wenn eine Taste gedrückt wird und das Steuerelement aktiv ist. Dieses Verfahren kann auch verwendet werden, andere vordefinierten Ereignisse hinzuzufügen. Ersetzen Sie den Namen der ausgewählten Basisereignis für KeyPress.  
  
#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>So fügen Sie die vordefinierten KeyPress-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Add Event**.  
  
     Dies öffnet den Assistenten zum Hinzufügen eines Ereignisses.  
  
4.  In der **Ereignisname** Dropdown-Liste `KeyPress`.  
  
5.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a>Fügen Sie-Assistent ändert für vordefinierte Ereignisse hinzu.  
 Da vordefinierte Ereignisse auf das Steuerelement Basisklasse behandelt werden, den Assistenten zum Hinzufügen von Ereignis nicht die Klassendeklaration in keiner Weise geändert. Er fügt das Ereignis zu Ereignis-steuerelementzuordnung hinzu und erstellt einen Eintrag in seiner. IDL-Datei. Die folgende Zeile wird das Steuerelement ereigniszuordnung, befindet sich in der Implementierung des Steuerelements-Klasse hinzugefügt (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 Hinzufügen dieses Codes wird eine KeyPress-Ereignis ausgelöst, wenn eine `WM_CHAR` Nachricht empfangen wird und das Steuerelement aktiv ist. Das KeyPress-Ereignis kann zu anderen Zeiten durch Aufrufen der Funktion Auslösen von Ereignissen ausgelöst werden (z. B. `FireKeyPress`) von innerhalb der Steuerungscode.  
  
 Den Assistenten zum Hinzufügen hinzugefügt des Steuerelements die folgende Codezeile. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 Diese Zeile ordnet das KeyPress-Ereignis mit der standardmäßigen Dispatch-ID und der Container kann das KeyPress-Ereignis zu erwarten.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
