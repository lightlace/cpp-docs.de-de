---
title: "How to: Open a Resource Script File Outside of a Project (Standalone)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - ".rc files, viewing resources"
  - "resource script files, viewing resources"
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Open a Resource Script File Outside of a Project (Standalone)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Ressourcen in einer RC\-Datei anzeigen, ohne dass ein Projekt geöffnet sein muss.  Die RC\-Datei wird in einem Dokumentfenster geöffnet, anstatt in dem Fenster [Ressourcenansicht](../windows/resource-view-window.md) \(wie beim Öffnen der Datei innerhalb eines Projekts\).  
  
> [!NOTE]
>  Dies ist eine wichtige Unterscheidung, da einige Befehle nur verfügbar sind, wenn die Datei eigenständig \(außerhalb eines Projekts\) geöffnet wird.  Beispielsweise können Sie eine Datei nur dann in einem anderen Format oder unter einem anderen Dateinamen speichern, wenn die Datei außerhalb eines Projekts geöffnet wird \(der Befehl  **Speichern unter** ist nicht verfügbar, wenn eine Datei innerhalb eines Projekts geöffnet wird\).  
  
### Öffnen einer RC\-Datei außerhalb eines Projekts  
  
1.  Wählen Sie im Menü **Datei** die Option **Öffnen**, und klicken Sie dann auf **Datei**.  
  
2.  Navigieren Sie im Dialogfeld **Datei öffnen** zur Ressourcenskriptdatei, die Sie anzeigen möchten, markieren Sie die Datei, und klicken Sie auf **Öffnen**.  
  
    > [!NOTE]
    >  Wenn Sie das Projekt zuerst öffnen \(**Datei**, **Öffnen**, **Projekt**\), sind einige Befehle nicht verfügbar.  Eine Datei „eigenständig“ zu öffnen, bedeutet, sie zu öffnen, ohne erst das Projekt zu laden.  
  
 Informationen zum Öffnen und Anzeigen der Ressourcendatei im Textformat finden Sie unter [Bearbeiten einer Ressourcenskriptdatei \(.rc\)](../windows/how-to-open-a-resource-script-file-in-text-format.md).  
  
#### Öffnen mehrerer RC\-Dateien außerhalb eines Projekts  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig.  Öffnen Sie beispielsweise Source1.rc und Source2.rc.  
  
    1.  Wählen Sie im Menü **Datei** die Option **Öffnen**, und klicken Sie dann auf **Datei**.  
  
    2.  Navigieren Sie im Dialogfeld **Datei öffnen** zur ersten Ressourcenskriptdatei, die Sie öffnen möchten \(Source1.rc\), markieren Sie die Datei, und klicken Sie auf **Öffnen**.  
  
    3.  Wiederholen Sie den vorherigen Schritt, um die zweite RC\-Datei \(Source2.rc\) zu öffnen.  
  
         Die RC\-Dateien sind nun in separaten Dokumentfenstern geöffnet.  
  
2.  Wenn beide RC\-Dateien geöffnet sind, ordnen Sie die Fenster so an, dass sie gleichzeitig angezeigt werden:  
  
    -   Wählen Sie im Menü **Fenster** die Option **Neue horizontale Registerkartengruppe** oder **Neue vertikale Registerkartengruppe**.  
  
         \- oder \-  
  
    -   Klicken Sie mit der rechten Maustaste auf eine der RC\-Dateien, und wählen Sie **Neue horizontale Registerkartengruppe** oder **Neue vertikale Registerkartengruppe** aus dem Kontextmenü.  
  
> [!NOTE]
>  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)