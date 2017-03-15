---
title: "Erstellen eines MFC-ActiveX-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Erstellen"
  - "MFC ActiveX-Steuerelemente [C++], Erstellen"
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Erstellen eines MFC-ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX\-Steuerelementprogramme sind modulare Programme, die einer übergeordneten Anwendung eine bestimmte Funktionalität verleihen.  Steuerelemente sind beispielsweise Schaltflächen, die in einem Dialogfeld verwendet werden, oder Symbolleisten, die auf einer Webseite verwendet werden.  
  
 Am einfachsten erstellen Sie ein MFC\-ActiveX\-Steuerelement, indem Sie den [MFC\-ActiveX\-Steuerelement\-Assistenten](../../mfc/reference/mfc-activex-control-wizard.md) verwenden.  
  
### So erstellen Sie ein MFC\-ActiveX\-Steuerelement mit dem MFC\-ActiveX\-Steuerelement\-Assistenten  
  
1.  Folgen Sie den Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C\+\+\-Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Vorlagenbereich Vorlagen das Symbol **MFC\-ActiveX\-Steuerelement** aus, um den MFC\-ActiveX\-Steuerelement\-Assistenten zu öffnen.  
  
3.  Definieren Sie die [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [Steuerelementnamen](../../mfc/reference/control-names-mfc-activex-control-wizard.md) und [Steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) mit dem MFC\-ActiveX\-Steuerelement\-Assistenten.  
  
    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.  
  
4.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt in der Entwicklungsumgebung zu öffnen.  
  
 Nachdem Sie das Projekt erstellt haben, können Sie die Dateien im **Projektmappen\-Explorer** anzeigen.  Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt".  Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual C\+\+\-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
 Nachdem Sie das Projekt erstellt haben, können Sie mithilfe der Code\-Assistenten [Funktionen](../../ide/add-member-function-wizard.md), [Variablen](../../ide/add-member-variable-wizard.md), [Ereignisse](../../ide/add-event-wizard.md), [Eigenschaften](../../ide/names-add-property-wizard.md) und [Methoden](../../ide/add-method-wizard.md) hinzufügen.  Weitere Informationen zum Anpassen von ActiveX\-Steuerelementen finden Sie unter [MFC\-ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](assetId:///4ff8881d-0daf-47e7-bfe7-774c625031b4)