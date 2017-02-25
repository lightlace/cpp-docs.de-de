---
title: "Editing Parts of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "Image editor [C++], editing images"
  - "Clipboard [C++], pasting"
  - "images [C++], editing"
  - "images [C++], deleting selected parts"
  - "images [C++], copying selected parts"
  - "images [C++], moving selected parts"
  - "images [C++], dragging and replicating selected parts"
  - "images [C++], pasting into"
  - "graphics [C++], editing"
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Editing Parts of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für eine [Markierung](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md) können Sie Standardbearbeitungsoperationen ausführen, wie Ausschneiden, Kopieren, Löschen und Verschieben. Dabei spielt es keine Rolle, ob die Markierung das gesamte Bild oder nur einen Ausschnitt umfasst.  Da der Grafik\-Editor die Zwischenablage verwendet, können Sie Bilder zwischen der Grafik\-Editor und andere Anwendungen für Windows übertragen.  
  
 Zusätzlich können Sie die Größe der Markierung ändern, und zwar unabhängig davon, ob das gesamte Bild oder nur ein Ausschnitt markiert ist.  
  
### So schneiden Sie die aktuelle Markierung aus und kopieren sie in die Zwischenablage  
  
1.  Klicken Sie im Menü **Bearbeiten** auf **Ausschneiden**.  
  
### So kopieren Sie die Markierung  
  
1.  Positionieren Sie den Mauszeiger auf einer beliebigen Stelle in oder auf dem Markierungsrahmen, nicht aber auf den Ziehpunkten.  
  
2.  Halten Sie die **STRG**\-TASTE gedrückt, während Sie die Markierung auf eine neue Position ziehen.  Der ursprünglich markierte Bereich wird nicht geändert.  
  
3.  Um die Markierung an der aktuellen Position in das Bild zu kopieren, klicken Sie auf eine Stelle außerhalb des Markierungscursors.  
  
### So fügen Sie den Inhalt der Zwischenablage in ein Bild ein  
  
1.  Wählen Sie im Menü **Bearbeiten** den Befehl **Einfügen**.  
  
     Der Inhalt der Zwischenablage, der sich innerhalb des Markierungsrahmens befindet, wird in der oberen linken Ecke des Fensterbereichs angezeigt.  
  
2.  Positionieren Sie den Mauszeiger innerhalb des Markierungsrahmens, und ziehen Sie das Bild auf die gewünschte Position im Bild.  
  
3.  Um das Bild an der neuen Position zu verankern, klicken Sie auf eine Stelle außerhalb des Markierungsrahmens.  
  
### So löschen Sie die aktuelle Markierung, ohne sie in die Zwischenablage zu verschieben  
  
1.  Wählen Sie im Menü **Bearbeiten** den Befehl **Löschen**.  
  
     Der ursprünglich markierte Bereich wird mit der aktuellen Hintergrundfarbe gefüllt.  
  
    > [!NOTE]
    >  Die Befehle Ausschneiden, Kopieren, Einfügen und Löschen können im Fenster Ressourcenansicht durch einen Klick mit der rechten Maustaste ausgewählt werden.  
  
### So verschieben Sie die Markierung  
  
1.  Positionieren Sie den Mauszeiger auf einer beliebigen Stelle in oder auf dem Markierungsrahmen, nicht aber auf den Ziehpunkten.  
  
2.  Ziehen Sie die Markierung auf die neue Position.  
  
3.  Um die Markierung im Bild an der neuen Position zu verankern, klicken Sie auf eine Stelle außerhalb des Markierungsrahmens.  
  
 Weitere Informationen zum Zeichnen mit einer Auswahl finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../mfc/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Kein  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)