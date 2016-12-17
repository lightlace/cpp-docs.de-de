---
title: "Adding Event Handlers for Dialog Box Controls"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialog editor, adding event handlers to controls"
  - "controls [C++], event handlers"
  - "dialog box controls, events"
  - "event handlers, for dialog box controls"
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Event Handlers for Dialog Box Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Dialogfeldern, die in einem Projekt bereits einer Klasse zugeordnet sind, können Ereignishandler mithilfe einiger vorteilhafter Schnellverfahren erstellt werden.  Sie können entweder für das Standardbenachrichtigungsereignis des Steuerelements oder für eine relevante Windows\-Meldung schnell einen Handler erstellen.  
  
#### So erstellen Sie einen Handler für das Standardbenachrichtigungsereignis des Steuerelements  
  
1.  Doppelklicken Sie auf das Steuerelement.  Der Text\-Editor wird geöffnet.  
  
2.  Geben Sie Handlercode für die Steuerelementbenachrichtigung im Text\-Editor ein.  
  
#### So erstellen Sie einen Handler für relevante Windows\-Meldungen  
  
1.  Klicken Sie auf das Steuerelement, dessen Benachrichtigungsereignis verarbeitet werden soll.  
  
2.  Klicken Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) auf die Schaltfläche **Steuerelementereignisse**, um die Liste der allgemeinen, mit dem Steuerelement verknüpften Windows\-Ereignisse einzublenden.  Im Dialogfeld **Info** werden für die Standardschaltfläche **OK** z. B. die folgenden Benachrichtigungsereignisse aufgelistet:  
  
     **BN\_CLICKED**  
  
     **BN\_DOUBLECLICKED**  
  
     **BN\_KILLFOCUS**  
  
     **BN\_SETFOCUS**  
  
    > [!NOTE]
    >  Sie können auch das Dialogfeld auswählen und auf die Schaltfläche **Steuerelementereignisse** klicken, um die Liste der allgemeinen Windows\-Ereignisse für alle Steuerelemente im Dialogfeld anzuzeigen.  
  
3.  Klicken Sie im **Eigenschaftenfenster** auf die rechte Spalte neben dem zu verarbeitenden Ereignis, und wählen Sie dann den vorgeschlagenen Namen für das Benachrichtigungsereignis aus \(durch **OnBnClickedOK** wird z. B. **BN\_CLICKED** verarbeitet\).  
  
    > [!NOTE]
    >  Anstatt den Standardnamen des Ereignishandlers auszuwählen, können Sie auch einen eigenen Ereignishandlernamen angeben.  
  
     Nachdem Sie das Ereignis ausgewählt haben, öffnet Visual Studio den Text\-Editor und zeigt den Ereignishandlercode an.  Folgender Code wird beispielsweise für das Standardereignis **OnBnClickedOK** hinzugefügt:  
  
    ```  
    void CAboutDlg::OnBnClickedOk(void)  
    {  
       // TODO: Add your control notification handler code here  
    }  
    ```  
  
 Wenn Sie den Ereignishandler einer anderen Klasse hinzufügen möchten als derjenigen, durch die das Dialogfeld implementiert wird, verwenden Sie den [Ereignishandler\-Assistenten](../ide/event-handler-wizard.md).  Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Win32  
  
## Siehe auch  
 [Default Control Events](../mfc/default-control-events.md)   
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)