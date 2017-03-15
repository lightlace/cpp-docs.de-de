---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EVENT__STOCK_ERROR"
  - "EVENT__STOCK_READYSTATECHANGE"
  - "ReadyStateChange"
  - "EVENT__STOCK_MOUSEMOVE"
  - "EVENT__STOCK_MOUSEUP"
  - "EVENT__STOCK_DBLCLICK"
  - "KeyPress"
  - "EVENT__STOCK_KEYDOWN"
  - "EVENT__STOCK"
  - "EVENT__STOCK_MOUSEDOWN"
  - "EVENT__STOCK_KEYPRESS"
  - "EVENT__STOCK_CLICK"
  - "EVENT__STOCK_KEYUP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EVENT_STOCK-Präfix"
  - "EVENT_STOCK_CLICK-Ereignis"
  - "EVENT_STOCK_DBLCLICK-Ereignis"
  - "EVENT_STOCK_ERROREVENT-Ereignis"
  - "EVENT_STOCK_KEYDOWN-Ereignis"
  - "EVENT_STOCK_KEYPRESS-Ereignis"
  - "EVENT_STOCK_KEYPRESS-Makro"
  - "EVENT_STOCK_KEYUP-Ereignis"
  - "EVENT_STOCK_MOUSEDOWNEreignis"
  - "EVENT_STOCK_MOUSEMOVE-Ereignis"
  - "EVENT_STOCK_MOUSEUP-Ereignis"
  - "EVENT_STOCK_READYSTATECHANGE-Ereignis"
  - "Ereignisse [C++], Bestand"
  - "FireClick-Ereignis"
  - "FireDblClick-Ereignis"
  - "FireError-Ereignis"
  - "FireKeyDown-Ereignis"
  - "FireKeyPress-Ereignis"
  - "FireKeyUp-Ereignis"
  - "FireMouseDown-Ereignis"
  - "FireMouseMove-Ereignis"
  - "FireMouseUp-Ereignis"
  - "KeyPress-Ereignis"
  - "MFC-ActiveX-Steuerelemente, Ereignisse"
  - "ReadyStateChange-Ereignis"
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Ereignissen zu einem ActiveX-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vordefinierte Ereignisse unterscheiden sich von benutzerdefinierten Ereignissen, da sie automatisch durch Klasse [COleControl](../mfc/reference/colecontrol-class.md) ausgelöst werden.  `COleControl` enthält vordefinierte Memberfunktionen, die Ereignisse auslösen, erstellten über allgemeine Aktionen.  Einige allgemeine Aktionen, die von `COleControl` implementiert werden, gehören von Einzel\- und Doppelklicke auf dem Steuerelement, den Tastaturereignissen und Änderungen im Zustand der Maustasten.  Ereigniszuordnungseinträge für vordefinierte Ereignisse werden immer vom **EVENT\_STOCK** Präfix vorangestellt.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> Vordefinierte Ereignisse unterstützt im Assistenten zum Hinzufügen von Ereignissen  
 Die `COleControl`\-Klasse stellt zehn vordefinierte Ereignisse, aufgeführt in der folgenden Tabelle.  Sie können die Ereignisse festlegen, die Sie im Steuerelement mit [Assistent zum Hinzufügen von Ereignissen](../ide/add-event-wizard.md) möchten.  
  
### Vordefinierte Ereignisse  
  
|Ereignis|Auslösen von Funktion|Kommentare|  
|--------------|---------------------------|----------------|  
|Auszuwählende Option|**ungültiges FireClick\(\)**|Ausgelöste, wenn das Steuerelement die Maus erfasst wird, entweder **BUTTONUP** \(links, Mitte oder rechts\) Nachricht empfangen wird, und die Schaltfläche wird über dem Steuerelement freigegeben.  Die vordefinierten Ereignisse MouseDown und MouseUp treten vor diesem Ereignis auf.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_CLICK\( \)**|  
|DblClick|**ungültiges FireDblClick\(\)**|Ähnlich wie Klick jedoch ausgelöst, wenn eine **BUTTONDBLCLK** Meldung empfängt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_DBLCLICK\( \)**|  
|Fehler|**void FireError\( SCODE**  *scode* **, LPCSTR**  `lpszDescription` **, UINT**  `nHelpID`  **\= 0 \)**|Wird ausgelöst, wenn ein Fehler in des ActiveX\-Steuerelements außerhalb des Bereichs eines Methodenaufrufs oder des Eigenschaftenzugriffs auftritt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_ERROREVENT\( \)**|  
|KeyDown|**void FireKeyDown\( short**  `nChar` **, short**  `nShiftState`  **\)**|Wird ausgelöst, wenn `WM_SYSKEYDOWN` oder `WM_KEYDOWN` eine Meldung empfängt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_KEYDOWN\( \)**|  
|KeyPress|**void FireKeyPress\( short\***  `pnChar`  **\)**|Wird ausgelöst, wenn `WM_CHAR` eine Meldung empfängt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_KEYPRESS\( \)**|  
|KeyUp|**void FireKeyUp\( short**  `nChar` **, short**  `nShiftState`  **\)**|Wird ausgelöst, wenn `WM_SYSKEYUP` oder `WM_KEYUP` eine Meldung empfängt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_KEYUP\( \)**|  
|MouseDown|**void FireMouseDown\( short**  `nButton` **, short**  `nShiftState` **, float**  *x* *y*  **\) , float**|Ausgelöstes ggf. **BUTTONDOWN** \(links, Mitte oder rechts\) empfangen wird.  Die Maus wird aufgezeichnet, unmittelbar bevor das Ereignis ausgelöst wird.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_MOUSEDOWN\( \)**|  
|MouseMove|**void FireMouseMove\( short**  `nButton` **, short**  `nShiftState` **, float**  *x* *y*  **\) , float**|Wird ausgelöst, wenn `WM_MOUSEMOVE` eine Meldung empfängt.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_MOUSEMOVE\( \)**|  
|MouseUp|**void FireMouseUp\( short**  `nButton` **, short**  `nShiftState` **, float**  *x* *y*  **\) , float**|Ausgelöstes ggf. **BUTTONUP** \(links, Mitte oder rechts\) empfangen wird.  Die Mausauswahl wird freigegeben, bevor das Ereignis ausgelöst wird.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_MOUSEUP\( \)**|  
|ReadyStateChange|**ungültiges FireReadyStateChange\(\)**|Wird ausgelöst, als Steuerelement zum nächsten Zustand Bereit aufgrund der Datenmenge erhalten.<br /><br /> Ereigniszuordnungseintrag: **EVENT\_STOCK\_READYSTATECHANGE\( \)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Hinzufügen eines vordefinierten Ereignisses mithilfe des Assistenten zum Hinzufügen von Ereignissen  
 Das Hinzufügen vordefinierter Ereignissen erfordert weniger Arbeitsaufgaben, als benutzerdefinierten Ereignissen, da die Auslösung des tatsächlichen Ereignisses automatisch durch die Basisklasse, behandelt werden `COleControl` hinzugefügt.  In der folgenden Prozedur fügt einem vordefinierten Ereignis ein Steuerelement hinzu, das mit [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md) entwickelt wurde.  Das Ereignis, aufgerufen KeyPress, wird ausgelöst, wenn eine Taste gedrückt wird und welches Steuerelement aktiv ist.  Diese Prozedur kann auch verwendet werden, um andere vordefinierte Ereignisse hinzuzufügen.  Ersetzen Sie den ausgewählten vordefinierten Ereignisnamen für KeyPress.  
  
#### Um das KeyPress hinzuzufügen vorrätigen Artikel Sie Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignissen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Klicken Sie in der Klassenansicht auf die ActiveX\-Steuerelementklasse mit der rechten Maustaste, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Ereignis hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Ereignissen.  
  
4.  In der Dropdownliste **Ereignisname** Option `KeyPress` aus.  
  
5.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> Assistent zum Hinzufügen von Ereignissenen\-Änderungen für vordefinierte Ereignisse  
 Da vordefinierte Ereignisse durch die Basisklasse des Steuerelements behandelt werden, ändert der Assistent zum Hinzufügen von Ereignissen nicht die Klassendeklaration in jeder Hinsicht.  Sie fügt das Ereignis der Ereigniszuordnung des Steuerelements hinzu und macht einen Eintrag in die IDL\-Datei.  In der folgenden Zeile wird der Ereigniszuordnung des Steuerelements hinzugefügt, in der Steuerelementklasse \(.CPP\):  
  
 [!CODE [NVC_MFC_AxUI#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#5)]  
  
 Diesem Code hinzufügen, löst ein KeyPress\-Ereignis aus, wenn `WM_CHAR` eine Meldung ist und welches Steuerelement aktiv ist.  Das KeyPress\-Ereignis kann indem seine Auslösenfunktion \(beispielsweise `FireKeyPress`\), aus dem Steuerelementcode zu anderen Zeiten ausgelöst werden, aufgerufen.  
  
 Der Assistent zum Hinzufügen von Ereignissen wird die folgende Codezeile der IDL\-Datei des Steuerelements hinzu:  
  
 [!CODE [NVC_MFC_AxUI#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#6)]  
  
 Diese Zeile ordnet das KeyPress\-Ereignis mit der Standarddispatch\-id zu und der Container, um das KeyPress\-Ereignis vorauszusehen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)