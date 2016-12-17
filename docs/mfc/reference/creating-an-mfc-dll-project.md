---
title: "Erstellen eines MFC-DLL-Projekts"
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
  - "vc.appwiz.mfcdll.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Erstellen"
  - "DLLs [C++], MFC"
  - "MFC-DLLs [C++], Erstellen von Projekten"
  - "Projekte [C++], Erstellen"
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines MFC-DLL-Projekts
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine MFC\-DLL ist eine Binärdatei und fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig verwendet werden kann.  Am einfachsten erstellen Sie ein MFC\-DLL\-Projekt mit dem MFC\-DLL\-Assistenten.  
  
> [!NOTE]
>  Die in der IDE dargestellten Features können sich je nach den aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Features unterscheiden.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](assetId:///22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein MFC\-DLL\-Projekt mit dem MFC\-DLL\-Assistenten  
  
1.  Folgen Sie den Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C\+\+\-Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Hinweis** Wählen Sie im Dialogfeld **Neues Projekt** das Symbol `MFC DLL` im Vorlagenbereich aus, um den MFC DLL\-Assistenten zu öffnen.  
  
1.  Definieren Sie die Anwendungseinstellungen auf der Seite [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-dll-wizard.md) des [MFC\-DLL\-Assistenten](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.  
  
2.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt in **Projektmappen\-Explorer** zu öffnen.  
  
 Nachdem Sie das Projekt erstellt haben, können Sie die erstellten Dateien in Projektmappen\-Explorer anzeigen.  Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt".  Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual C\+\+\-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## Siehe auch  
 [Visual C\+\+\-Projekttypen](../Topic/Debugging%20Preparation:%20Visual%20C++%20Project%20Types.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](assetId:///4ff8881d-0daf-47e7-bfe7-774c625031b4)