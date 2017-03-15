---
title: "Gewusst wie: Hinzuf&#252;gen von Men&#252;band-Steuerelementen und Ereignishandlern | Microsoft Docs"
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
  - "Ereignishandler, Hinzufügen"
  - "Menübandsteuerelemente, Hinzufügen"
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gewusst wie: Hinzuf&#252;gen von Men&#252;band-Steuerelementen und Ereignishandlern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Menübandsteuerelemente sind Elemente, wie Schaltflächen und Kombinationsfelder, die Sie Bereiche hinzufügen.  Bereiche sind Bereiche der Menübandleiste, die eine Gruppe verwandter Steuerelemente anzeigen.  
  
 In diesem Thema öffnen Sie den Menüband\-Designer, fügen eine Schaltfläche hinzu und stellen dann ein Ereignis, Anzeigen "Hello World".  
  
### So öffnen den Menüband\-Designer  
  
1.  In Visual Studio im Menü **Ansicht**, klicken Sie auf **Ressourcenansicht**.  
  
2.  Doppelklicken Sie in **Ressourcenansicht** auf die Menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.  
  
### So fügen Sie eine Schaltfläche und ein Ereignishandler hinzugefügt  
  
1.  Von **Symbolleiste** auf **Schaltfläche** und ziehen Sie es an einem Bereich in der Entwurfsoberfläche.  
  
2.  Klicken Sie auf die Schaltfläche mit der rechten Maustaste auf  **Ereignishandler hinzufügen**.  
  
3.  In **Ereignishandler\-Assistent** bestätigen Sie die Standardeinstellungen und klicken Sie auf **Hinzu\/Bearb.**.  Weitere Informationen finden Sie unter [Ereignishandler\-Assistent](../ide/event-handler-wizard.md).  
  
4.  Fügen Sie im Code\-Editor den folgenden Code in die Handlerfunktion hinzu:  
  
    ```  
    MessageBox((LPCTSTR)L"Hello World");  
    ```  
  
## Siehe auch  
 [RibbonGadgets\-Beispiel: Anwendung für Minianwendungen auf dem Menüband](../top/visual-cpp-samples.md)   
 [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md)