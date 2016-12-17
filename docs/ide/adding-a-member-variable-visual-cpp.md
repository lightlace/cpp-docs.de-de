---
title: "Hinzuf&#252;gen einer Membervariablen (Visual C++)"
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
  - "vc.codewiz.classes.member.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Membervariablen"
  - "Membervariablen, Hinzufügen"
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer Membervariablen (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Klassenansicht können Sie einer Klasse eine Membervariable hinzufügen.  Membervariablen sind entweder für den [Datenaustausch und die Datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) bestimmt oder allgemein gebräuchlich.  Der Assistent zum Hinzufügen von Membervariablen wurde speziell zu dem Ziel entwickelt, die relevanten Informationen aufzunehmen und dazu zu verwenden, um Elemente an den geeigneten Stellen in die Quelldateien einzufügen.  Sie können eine Membervariable mithilfe des [Dialog\-Editors](../mfc/dialog-editor.md) in der [Ressourcenansicht](../windows/resource-view-window.md) oder aber in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) hinzufügen.  
  
> [!NOTE]
>  Beim Entwerfen und Implementieren eines Dialogfelds erscheint es Ihnen möglicherweise effizienter, die Dialogfeld\-Steuerelemente mit dem Dialog\-Editor hinzuzufügen und anschließend die Membervariablen des Steuerelements zu implementieren.  
  
### So fügen Sie ein Dialogfeld\-Steuerelement mit dem Assistenten zum Hinzufügen von Membervariablen in der Ressourcenansicht hinzu  
  
1.  Erweitern Sie in der Ressourcenansicht den Projektknoten und den Dialogknoten, um die Dialogfelder des Projekts aufzulisten.  
  
2.  Doppelklicken Sie auf das Dialogfeld, dem Sie die Membervariable hinzufügen möchten, um es im Dialog\-Editor zu öffnen.  
  
3.  Klicken Sie im Dialogfeld, das im Dialog\-Editor angezeigt wird, mit der rechten Maustaste auf das Steuerelement, dem Sie die Membervariable hinzufügen möchten.  
  
4.  Klicken Sie im Kontextmenü auf **Variable hinzufügen**, um den [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) aufzurufen.  
  
    > [!NOTE]
    >  Das Feld **Steuerelement\-ID** enthält bereits einen Standardwert.  
  
5.  Geben Sie Informationen in die entsprechenden Assistentenfelder ein.  Weitere Informationen finden Sie unter [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md).  
  
6.  Klicken Sie auf **Fertig stellen**, um dem Projekt den Definitions\- und Implementierungscode hinzuzufügen und den Assistenten zu schließen.  
  
### So fügen Sie eine Membervariable mit dem Assistenten zum Hinzufügen von Membervariablen in der Klassenansicht hinzu  
  
1.  Erweitern Sie in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) den Projektknoten, um die Projektklassen anzuzeigen.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Klasse, der Sie eine Variable hinzufügen möchten.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Variable hinzufügen**, um den Assistenten zum Hinzufügen von Membervariablen anzuzeigen.  
  
4.  Geben Sie Informationen in die entsprechenden Assistentenfelder ein.  Ausführliche Informationen finden Sie unter [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md).  
  
5.  Klicken Sie auf **Fertig stellen**, um dem Projekt den Definitions\- und Implementierungscode hinzuzufügen und den Assistenten zu schließen.  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)