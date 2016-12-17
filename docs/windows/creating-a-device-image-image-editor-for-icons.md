---
title: "Creating a Device Image (Image Editor for Icons)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.icon"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "icons [C++], creating"
  - "display devices"
  - "display devices, creating image"
  - "images [C++], creating for display devices"
  - "icons [C++], inserting"
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Device Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine neue Symbol\- oder Cursorressource erstellen, legt der Grafik\-Editor zunächst ein Bild in einem spezifischen Stil an \(32 × 32, 16 Farben für Symbole und 32 × 32, Monochrom für Cursor\).  Anschließend können Sie dem anfänglichen Symbol oder Cursor Bilder in unterschiedlichen Größen und Stilen hinzufügen und die jeweiligen zusätzlichen Bilder nach Bedarf für die verschiedenen Anzeigegeräte bearbeiten.  Sie können ein Bild auch bearbeiten, indem Sie einen Ausschneide\- und Einfügevorgang von einem vorhandenen Bildtyp oder von einer Bitmap ausführen, die in einem Grafikprogramm erstellt wurde.  Weitere Informationen über die in Windows verwendeten Symbolgrößen finden Sie unter [Icons](_win32_Icons_cpp) in der Windows SDK\-Dokumentation.  
  
 Wenn Sie die Symbol\- oder Cursorressource im [Grafik\-Editor](../mfc/image-editor-for-icons.md) öffnen, wird standardmäßig das Bild geöffnet, das dem aktuellen Anzeigegerät am ehesten entspricht.  
  
### So erstellen Sie ein neues Symbol oder einen neuen Cursor  
  
1.  Klicken Sie in der [Ressourcenansicht](../windows/resource-view-window.md) mit der rechten Maustaste auf die RC\-Datei, und wählen Sie dann **Ressource einfügen** aus dem Kontextmenü.  \(Enthält die RC\-Datei bereits eine Bildressource, z. B. einen Cursor, klicken Sie einfach mit der rechten Maustaste auf den Ordner **Cursor** und wählen im Kontextmenü **Cursor einfügen** aus.\)  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im [Dialogfeld "Ressource einfügen"](../windows/add-resource-dialog-box.md) **Symbol** oder **Cursor**, und klicken Sie auf **Neu**.  Für Symbole erstellen Sie hiermit eine Symbolressource mit 32 × 32 Pixel und 16 Farben.  Für Cursor wird ein monochromes Bild \(2 Farben\) mit 32 × 32 Pixel erstellt.  
  
     Wenn im Dialogfeld **Ressource einfügen** neben dem Bildressourcentyp ein Pluszeichen \(**\+**\) angezeigt wird, bedeutet dies, dass Symbolleistenvorlagen verfügbar sind.  Klicken Sie auf das Pluszeichen, um die Vorlagenliste zu erweitern, markieren Sie eine Vorlage, und klicken Sie auf **Neu**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 None  
  
## Siehe auch  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)