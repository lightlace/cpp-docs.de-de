---
title: "Creating a New Toolbar Button | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Toolbar editor, creating buttons"
  - "toolbar buttons (in Toolbar editor), button image"
  - "toolbar buttons (in Toolbar editor), creating"
  - "toolbar buttons (in Toolbar editor)"
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating a New Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So erstellen Sie eine neue Symbolleisten\-Schaltfläche  
  
1.  Erweitern Sie in der [Ressourcenansicht](../windows/resource-view-window.md) den Ressourcenordner \(z. B. **Projekt1.rc**\).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Erweitern Sie den Ordner **Symbolleiste**, und wählen Sie eine Symbolleiste zur Bearbeitung aus.  
  
3.  Weisen Sie der leeren Schaltfläche ganz rechts auf der Symbolleiste eine ID zu.  Bearbeiten Sie dazu z. B. die Eigenschaft **ID** im [Eigenschaftenfenster](../Topic/Properties%20Window.md).  Angenommen, eine Symbolleisten\-Schaltfläche soll dieselbe ID wie eine Menüoption erhalten.  In diesem Fall verwenden Sie das Dropdown\-Listenfeld, um die **ID** der Menüoption auszuwählen.  
  
     – oder –  
  
     Markieren Sie die leere Schaltfläche rechts auf der Symbolleiste \(in der Symbolleistenansicht\), und beginnen Sie mit dem Zeichnen.  Es wird eine standardmäßige Schaltflächenbefehls\-ID zugeordnet \(ID\_BUTTON\<n\>\).  
  
 Ein Bild, das als neue Schaltfläche verwendet werden soll, kann auch kopiert und in die Symbolleiste eingefügt werden.  
  
#### So fügen Sie einer Symbolleiste ein Bild als Schaltfläche hinzu  
  
1.  Öffnen Sie die Symbolleiste, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md) darauf doppelklicken.  
  
2.  Öffnen Sie dann das Bild, das der Symbolleiste hinzugefügt werden soll.  
  
    > [!NOTE]
    >  Wenn Sie das Bild in Visual Studio öffnen, wird es im Grafik\-Editor geöffnet.  Das Bild kann auch in anderen Grafikprogrammen geöffnet werden.  
  
3.  Wählen Sie im Menü **Bearbeiten** den Befehl **Kopieren**.  
  
4.  Wechseln Sie zu der Symbolleiste, indem Sie oben im Quellcodefenster auf die entsprechende Registerkarte klicken.  
  
5.  Wählen Sie im Menü **Bearbeiten** den Befehl **Einfügen**.  
  
     Das Bild wird als neue Schaltfläche auf der Symbolleiste angezeigt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 MFC oder ATL  
  
## Siehe auch  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)