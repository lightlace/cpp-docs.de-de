---
title: "Hinzuf&#252;gen eines Ereignishandlers (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ereignishandler, Hinzufügen"
  - "MSBuild, Eigenschaften"
  - "Eigenschaften [Visual Studio], MSBuild"
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen eines Ereignishandlers (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Ressourcen\-Editor können Sie mithilfe des [Ereignishandler\-Assistenten](../ide/event-handler-wizard.md) einen neuen Ereignishandler hinzufügen oder einen vorhandenen Ereignishandler für ein Dialogfeld\-Steuerelement bearbeiten.  
  
 Sie können der Klasse ein Ereignis hinzufügen, indem Sie das Dialogfeld mithilfe des [Eigenschaftenfensters](../Topic/Properties%20Window.md) implementieren.  Wenn Sie das Ereignis einer anderen Klasse als der Dialogfeldklasse hinzufügen möchten, verwenden Sie dazu den Ereignishandler\-Assistenten.  
  
### So fügen Sie einem Dialogfeld\-Steuerelement einen Ereignishandler hinzu  
  
1.  Doppelklicken Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf die Dialogfeldressource, um die Dialogfeldressource, die das Steuerelement enthält, im [Dialog\-Editor](../mfc/dialog-editor.md) zu öffnen.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Steuerelement, dessen Benachrichtigungsereignis Sie behandeln möchten.  
  
3.  Klicken Sie im Kontextmenü auf **Ereignishandler hinzufügen**, um den Ereignishandler\-Assistenten aufzurufen.  
  
4.  Wählen Sie im Feld **Meldungstyp** das Ereignis aus, das der im Feld **Klassenliste** markierten Klasse hinzugefügt werden soll.  
  
5.  Übernehmen Sie den Standardnamen im Feld **Funktionshandlername**, oder geben Sie den gewünschten Namen ein.  
  
6.  Klicken Sie auf **Hinzufügen und bearbeiten**, um dem Projekt den Ereignishandler hinzuzufügen und den Text\-Editor an der neuen Funktion zu öffnen, sodass Sie den entsprechenden Ereignishandlercode eingeben können.  
  
     Wenn der ausgewählte Meldungstyp bereits einen Ereignishandler für die markierte Klasse besitzt, ist anstelle der Schaltfläche Hinzufügen und bearbeiten die Schaltfläche Code bearbeiten auswählbar.  Klicken Sie auf Code bearbeiten, um den Text\-Editor an der vorhandenen Funktion zu öffnen.  
  
 Alternativ können Sie Ereignishandler auch über das [Eigenschaftenfenster](../Topic/Properties%20Window.md) hinzufügen.  Weitere Informationen finden Sie unter [Hinzufügen von Ereignishandlern für Dialogfeld\-Steuerelemente](../mfc/adding-event-handlers-for-dialog-box-controls.md).  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)