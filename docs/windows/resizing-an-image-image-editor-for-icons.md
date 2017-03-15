---
title: "Resizing an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "Image editor [C++], resizing images"
  - "graphics [C++], resizing"
  - "images [C++], resizing"
  - "resizing images"
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Resizing an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie sich der Grafik\-Editor beim Ändern der Bildgröße verhält, hängt davon ab, ob das gesamte Bild oder nur ein Bereich [markiert](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md) wurde.  
  
 Wenn die Markierung nur einen Teil des Bildes umfasst, verkleinert der Grafik\-Editor die Auswahl, indem er Zeilen oder Spalten von Pixeln löscht und die freigewordenen Bereiche mit der aktuellen Hintergrundfarbe füllt. Oder er streckt die Markierung, indem er Zeilen oder Spalten von Pixeln verdoppelt.  
  
 Wenn die Markierung das gesamte Bild enthält, wird das Bild vom Grafik\-Editor verkleinert oder gestreckt bzw. zugeschnitten oder erweitert.  
  
 Die Größe von Bildern kann auf zweifache Weise geändert werden: mithilfe der Ziehpunkte und im [Eigenschaftenfenster](../Topic/Properties%20Window.md).  Sie können die Ziehpunkte ziehen, um die Größe des gesamten Bildes oder eines Bildbereichs zu ändern.  Aktive Ziehpunkte sind ganz ausgefüllt.  Sie können keine Punkte ziehen, die hohl sind.  Im Eigenschaftenfenster kann nur die Größe des gesamten Bildes geändert werden und nicht die von Bildbereichen.  
  
 ![Ziehpunkte in einer Bitmap](../mfc/media/vcimageeditorsizinghandles.png "vcImageEditorSizingHandles")  
Ziehpunkte  
  
> [!NOTE]
>  Wenn Sie im [Dialogfeld "Rastereinstellungen"](../mfc/grid-settings-dialog-box-image-editor-for-icons.md) die Option Grobraster ausgewählt haben, rastet die Darstellung bei Größenänderungen an der nächsten Rasterlinie ein.  Wenn lediglich die Option **Pixelraster** ausgewählt ist \(Standardeinstellung\), rastet die Darstellung bei Größenänderungen am nächsten verfügbaren Pixel ein.  
  
-   [Größenänderung eines ganzen Bildes](../mfc/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Abschneiden oder Erweitern eines ganzen Bildes](../mfc/cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines ganzen Bildes](../mfc/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines Teiles eines Bildes](../mfc/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)