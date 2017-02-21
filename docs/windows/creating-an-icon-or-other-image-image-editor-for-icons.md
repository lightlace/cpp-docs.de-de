---
title: "Creating an Icon or Other Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps [C++]"
  - "images [C++], creating"
  - "resource toolbars"
  - "resources [Visual Studio], creating images"
  - "bitmaps [C++], creating"
  - "graphics [C++], creating"
  - "Image editor [C++], creating images"
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Creating an Icon or Other Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können ein neues Bild \(Bitmap, Symbol, Cursor oder Symbolleiste\) erstellen und dessen Darstellung mit dem Grafik\-Editor anpassen.  Außerdem können Sie eine neue Bitmap erstellen, die von einer [Vorlage](../windows/how-to-use-resource-templates.md) gebildet wurde.  
  
### So fügen Sie einem nicht verwalteten C\+\+\-Projekt eine neue Bildressource hinzu  
  
1.  Klicken Sie in der [Ressourcenansicht](../windows/resource-view-window.md) mit der rechten Maustaste auf die RC\-Datei, und wählen Sie dann **Ressource einfügen** aus dem Kontextmenü.  \(Enthält die RC\-Datei bereits eine Bildressource, z. B. einen Cursor, klicken Sie einfach mit der rechten Maustaste auf den Ordner **Cursor** und wählen im Kontextmenü **Cursor einfügen** aus.\)  
  
    > [!NOTE]
    >  **Hinweis** Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im [Dialogfeld "Ressource einfügen"](../windows/add-resource-dialog-box.md) den Typ der zu erstellenden Bildressource aus \(z. B. **Bitmap**\), und klicken Sie dann auf **Neu**.  
  
     Wenn im Dialogfeld **Ressource einfügen** neben dem Bildressourcentyp ein Pluszeichen \(**\+**\) angezeigt wird, bedeutet dies, dass Symbolleistenvorlagen verfügbar sind.  Klicken Sie auf das Pluszeichen, um die Vorlagenliste zu erweitern, markieren Sie eine Vorlage, und klicken Sie auf **Neu**.  
  
### So fügen Sie einem Projekt in einer .NET\-Programmiersprache eine neue Bildressource hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektordner \(z. B. **WindowsApplication1**\).  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen**, und wählen Sie dann **Neues Element hinzufügen** aus.  
  
3.  Erweitern Sie im Bereich **Kategorien** den Ordner **Lokale Projektelemente**, und wählen Sie dann **Ressourcen** aus.  
  
4.  Wählen Sie im Bereich **Vorlagen** den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
     Die Ressource wird dem Projekt im Projektmappen\-Explorer hinzugefügt und im [Grafik\-Editor](../mfc/image-editor-for-icons.md) geöffnet.  Nun können Sie das Bild mithilfe aller im Grafik\-Editor verfügbaren Tools bearbeiten.  Weitere Informationen darüber, wie Sie einem verwalteten Projekt Bilder hinzufügen, finden Sie unter [Laden eines Bildes zur Entwurfszeit](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md).  
  
    > [!NOTE]
    >  Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln.  Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  Weitere Informationen finden Sie unter [Erstellen von Ressourcendateien](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch*.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)