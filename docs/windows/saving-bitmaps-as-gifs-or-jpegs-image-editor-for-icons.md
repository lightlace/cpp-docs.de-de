---
title: "Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".gif files, saving bitmaps as"
  - "jpg files, saving bitmaps as"
  - "jpeg files, saving bitmaps as"
  - ".jpg files, saving bitmaps as"
  - "Image editor [C++], converting image formats"
  - "gif files, saving bitmaps as"
  - "bitmaps [C++], converting formats"
  - ".jpeg files, saving bitmaps as"
  - "graphics [C++], converting formats"
  - "images [C++], converting formats"
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Bitmap erstellen, wird das Bild im Bitmapformat \(**.bmp**\) angelegt.  Sie können das Bild jedoch auch als GIF\- oder JPEG\-Datei bzw. in anderen Grafikformaten speichern.  
  
> [!NOTE]
>  Dieses Verfahren kann weder auf Symbole noch auf Cursor angewendet werden.  
  
### So erstellen und speichern Sie eine Bitmap als GIF\- oder JPEG\-Datei  
  
1.  Wählen Sie im Menü **Datei** den Befehl **Öffnen**, und klicken Sie dann auf **Datei**.  
  
2.  Klicken Sie im **Dialogfeld "Neue Datei"** auf den Ordner **Visual C\+\+**, wählen Sie dann im Feld **Vorlagen** den Eintrag **Bitmapdatei \(.bmp\)** aus, und klicken Sie auf **Öffnen**.  
  
     Die Bitmap wird im Grafik\-Editor geöffnet.  
  
3.  Nehmen Sie ggf. Änderungen an der neuen Bitmap vor.  
  
4.  Klicken Sie im Menü **Datei** auf **Speichern *Dateiname*.bmp unter**, während die Bitmap im **Grafik**\-Editor geöffnet ist.  
  
5.  Geben Sie im Dialogfeld **Datei speichern unter** den Dateinamen sowie die Erweiterung ein, die im Feld **Dateiname** für das Dateiformat angezeigt werden soll.  Beispiel: **MeineDatei.gif**.  
  
     **Hinweis** Damit die Bitmap in einem anderen Dateiformat gespeichert werden kann, muss sie außerhalb des Projekts erstellt oder geöffnet werden.  Wenn Sie die Bitmap im Projekt erstellen oder öffnen, kann der Befehl **Speichern unter** nicht ausgewählt werden.  Weitere Informationen finden Sie unter [Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts \(eigenständig\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  Klicken Sie auf **Speichern**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Siehe auch  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)