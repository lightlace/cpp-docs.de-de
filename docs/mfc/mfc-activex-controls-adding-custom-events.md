---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Ereignissen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Click-Ereignis, Benutzerdefinierte Ereignisse"
  - "ClickIn-Ereignis"
  - "COleControl-Klasse, Benutzerdefinierte Ereignisse"
  - "Benutzerdefinierte Ereignisse"
  - "Benutzerdefinierte Ereignisse, Hinzufügen zu ActiveX-Steuerelementen"
  - "EVENT_CUSTOM-Makro"
  - "EVENT_CUSTOM-Präfix"
  - "Ereignisse [C++], ActiveX-Steuerelemente"
  - "FireClickIn-Ereignis"
  - "FireEvent-Methode, Hinzufügen von benutzerdefinierten Ereignissen"
  - "InCircle-Methode"
  - "MFC-ActiveX-Steuerelemente, Ereignisse"
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Ereignissen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Ereignisse unterscheiden sich aus vordefinierten Ereignissen, da sie nicht automatisch durch Klasse `COleControl` ausgelöst werden.  Ein benutzerdefiniertes Ereignis feststellt eine bestimmte Aktion, bestimmt vom Steuerelemententwickler, als Ereignis.  Die Ereigniszuordnungseinträge für benutzerdefinierte Ereignisse werden durch das Makro `EVENT_CUSTOM` dargestellt.  Der folgende Abschnitt implementiert ein benutzerdefiniertes Ereignis für ein ActiveX\-Steuerelementprojekt, das mithilfe des ActiveX\-Steuerelement\-Assistenten erstellt wurde.  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a> Hinzufügen eines benutzerdefinierten Ereignisses mit dem Assistenten zum Hinzufügen von Ereignissen  
 Im folgenden Verfahren wird ein bestimmtes benutzerdefiniertes Ereignis, ClickIn hinzu.  Sie können diese Prozedur verwenden, um andere benutzerdefinierte Ereignisse hinzuzufügen.  Ersetzen Sie den benutzerdefinierten Ereignisnamen und die Parameter für den ClickIn\-Ereignisnamen und Parameter zu variieren.  
  
#### So fügen Sie das benutzerdefinierte Ereignis ClickIn mit dem Assistenten zum Hinzufügen von Ereignissen hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Klicken Sie in der Klassenansicht auf die ActiveX\-Steuerelementklasse mit der rechten Maustaste, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Ereignis hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Ereignissen.  
  
4.  **Ereignisname** Im Feld zuerst wählen Sie jedes vorhandene Ereignis aus, klicken Sie auf das Optionsfeld **Benutzerdefiniert**, dann den Typ `ClickIn`.  
  
5.  Im Feld **Interner Name** geben Sie den Namen der Auslösenfunktion des Ereignisses ein.  Für dieses Beispiel verwenden Sie den Standardwert, der im Assistenten zum Hinzufügen von Ereignissen \(`FireClickIn`\) bereitgestellt wird.  
  
6.  Fügen Sie einen Parameter hinzu, die `xCoord`\-Typ \( `OLE_XPOS_PIXELS`\), mit **Parametername** und **Parametertyp** \-Steuerelemente.  
  
7.  Fügen Sie einen zweiten Parameter hinzu, die `yCoord`\-Typ \( `OLE_YPOS_PIXELS`\).  
  
8.  Klicken Sie auf **Fertig stellen**, um das Ereignis zu erstellen.  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a> Assistent zum Hinzufügen von Ereignissenen\-Änderungen für benutzerdefinierte Ereignisse  
 Wenn Sie ein benutzerdefiniertes Ereignis hinzufügen, wird der Assistent zum Hinzufügen von Ereignissen Änderungen der Steuerelementklasse vor. H, .CPP und IDL\-Dateien.  Die folgenden Codebeispiele zum ClickIn\-Ereignis bestimmt.  
  
 Die folgenden Zeilen werden an den Header hinzugefügt \(.H\) Datei der Steuerelementklasse:  
  
 [!CODE [NVC_MFC_AxUI#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#7)]  
  
 Dieser Code deklariert eine Inline\-Funktion Namen `FireClickIn`, die die [COleControl::FireEvent](../Topic/COleControl::FireEvent.md) dem Ereignis und den Parametern ClickIn aufruft, die, Sie mit dem Assistenten zum Hinzufügen von Ereignissen definiert haben.  
  
 Außerdem wird die folgende Zeile zur Ereigniszuordnung für das Steuerelement hinzugefügt, in der Implementierungsdatei \(.CPP\) der Steuerelementklasse:  
  
 [!CODE [NVC_MFC_AxUI#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#8)]  
  
 In diesem Code wird dem Ereignis ClickIn der Inlinefunktion `FireClickIn` auf und übergibt die Parameter, die Sie mit dem Assistenten zum Hinzufügen von Ereignissen definiert haben.  
  
 Schließlich wird die folgende Zeile in die IDL\-Datei des Steuerelements hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#9)]  
  
 Diese Zeile weist dem ClickIn\-Ereignis ein die bestimmte ID\-Nummer zu, aufgezeichnet von der Position des Ereignisses in der Assistent zum Hinzufügen von Ereignissenen\-Ereignisliste.  Die Liste des Eintrags im Ereignishandler ermöglicht einem Container, um das Ereignis zu bedenken.  Beispielsweise könnte der ausgeführt werden Handler zur Verfügungcode, wenn das Ereignis ausgelöst wird.  
  
##  <a name="_core_calling_fireclickin"></a> Aufrufen von FireClickIn  
 Nachdem Sie das benutzerdefinierte Ereignis ClickIn mit dem Assistenten zum Hinzufügen von Ereignissen hinzugefügt haben, müssen Sie entscheiden, sobald das Ereignis ausgelöst werden soll.  Sie erreichen dies, indem Sie `FireClickIn` aufrufen, wenn die richtige Aktion auftreten.  Für diese Diskussion verwendet das Steuerelement die `InCircle`\-Funktion innerhalb eines `WM_LBUTTONDOWN` Meldungshandlers, um das ClickIn\-Ereignis auszulösen, wenn ein Benutzer in einer Kreis\- oder elliptischen Bereichs klicken.  Im folgenden Verfahren werden die Handler `WM_LBUTTONDOWN` hinzu.  
  
#### Um einen Meldungshandler mit dem Assistenten zum Hinzufügen von Ereignissen hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  In der Klassenansicht wählen Sie die ActiveX\-Steuerelementklasse aus.  
  
3.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Meldungen**.  
  
     Das Eigenschaftenfenster zeigt eine Liste der Meldungen an, die das ActiveX\-Steuerelement bearbeitet werden können.  Jede Nachricht, die in Fettdruck wurde veranschaulicht wird, bereits eine Handlerfunktion, die an sie zugewiesen wird.  
  
4.  Wählen Sie im Eigenschaftenfenster die Meldung aus, die Sie bearbeiten möchten.  Wählen Sie für dieses Beispiel `WM_LBUTTONDOWN` aus.  
  
5.  Wählen Sie im Dropdown\-Listenfeld rechts, und wählen Sie **\<Add\> OnLButtonDown** aus.  
  
6.  Doppelklicken Sie auf die neue Handlerfunktion in der Klassenansicht, um zum Meldungshandlercode in der Implementierungsdatei \(.CPP\) des ActiveX\-Steuerelements zu springen.  
  
 Im folgenden Codebeispiel wird die **InCircle**\-Funktion auf, wenn auf die linke Maustaste im Steuerfensters geklickt wird.  Dieses Beispiel kann in der `WM_LBUTTONDOWN`\-Handlerfunktion, `OnLButtonDown` gefunden werden, in der Zusammenfassung [Circ\-Beispiel](../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_AxUI#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#10)]  
  
> [!NOTE]
>  Wenn der Assistent zum Hinzufügen von Ereignissen Meldungshandler für Maustastenaktionen erstellt wird, wird ein Aufruf an den gleichen Meldungshandler der Basisklasse automatisch hinzugefügt.  Entfernen Sie diesen Aufruf.  Wenn das Steuerelement eine der vordefinierten Mausmeldungen Meldungshandler verwendet, müssen die in der Basisklasse aufgerufen werden, um sicherzustellen, dass ordnungsgemäß Mausauswahl behandelt wird.  
  
 Im folgenden Beispiel löst sie das Ereignis aus, wenn der Klick innerhalb eines kreisförmigen oder elliptischen Bereichs im Steuerelement auftritt.  Um dieses Verhalten zu erreichen, können Sie die Funktion `InCircle` in der Implementierung des Steuerelements platzieren \(.CPP\):  
  
 [!CODE [NVC_MFC_AxUI#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#11)]  
  
 Außerdem müssen Sie die folgende Deklaration `InCircle` der Funktion des Headers des Steuerelements hinzufügen \(.H\) Datei:  
  
 [!CODE [NVC_MFC_AxUI#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#12)]  
  
##  <a name="_core_custom_events_with_stock_names"></a> Benutzerdefinierte Ereignisse mit vordefinierten Namen  
 Sie können benutzerdefinierte Ereignisse mit demselben Namen wie vordefinierte Ereignisse erstellt, z Sie beide im gleichen Steuerelement nicht implementieren können.  Beispielsweise können Sie ein benutzerdefiniertes Ereignis erstellen, das auf aufgerufen wird, der nicht ausgelöst, als der vordefinierte Ereignis Klick für gewöhnlich ausgelöst würde.  Sie könnten das Click\-Ereignis dann jederzeit auslösen, indem Sie seine Auslösenfunktion aufgerufen haben.  
  
 Im folgenden Verfahren wird ein benutzerdefiniertes Click\-Ereignis hinzu.  
  
#### Um ein benutzerdefiniertes Ereignis hinzufügen, das einen vordefinierten Ereignisnamen verwendet  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Klicken Sie in der Klassenansicht auf die ActiveX\-Steuerelementklasse mit der rechten Maustaste, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Ereignis hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Ereignissen.  
  
4.  In der Dropdownliste **Ereignisname** Wählen Sie einen vordefinierten Ereignisnamen aus.  In diesem Beispiel die Option **Klicken** aus.  
  
5.  Für **Ereignistyp** die Option **Benutzerdefiniert** aus.  
  
6.  Klicken Sie auf **Fertig stellen**, um das Ereignis zu erstellen.  
  
7.  Aufruf `FireClick` an den entsprechenden Stellen im Code.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)