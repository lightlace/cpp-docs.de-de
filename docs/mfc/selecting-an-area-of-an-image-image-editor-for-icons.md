---
title: "Selecting an Area of an Image (Image Editor for Icons)"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], image selection"
  - "Image editor [C++], selecting images"
  - "images [C++], selecting"
  - "cursors [C++], selecting areas of"
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting an Area of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit den Markierungstools können Sie einen Bereich eines Bildes definieren, den Sie ausschneiden, kopieren, löschen, umkehren, verschieben oder in seiner Größe ändern möchten.  Mit dem Tool **Rechteckauswahl** können Sie innerhalb eines Bildes einen rechteckigen Bereich definieren und markieren.  Mit dem Tool **Unregelmäßige Auswahl** können Sie um den Bereich, der zum Ausschneiden, Kopieren oder für eine andere Operation markiert werden soll, eine Freihandumrisslinie zeichnen.  
  
> [!NOTE]
>  Die Tools **Rechteckauswahl** und **Unregelmäßige Auswahl** lassen sich entweder anhand ihrer Symbole auf der [Symbolleiste des Grafik\-Editors](../mfc/toolbar-image-editor-for-icons.md) oder über die QuickInfos identifizieren, die zu jeder Schaltfläche auf der Symbolleiste des **Grafik\-Editors** angezeigt werden.  
  
 Aus der Markierung kann auch ein benutzerdefinierter Pinsel erstellt werden.  Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../mfc/creating-a-custom-brush-image-editor-for-icons.md).  
  
### So markieren Sie einen Bildbereich  
  
1.  Klicken Sie auf der Symbolleiste des Grafik\-Editors \(oder unter dem Befehl **Tools** im Menü **Bild**\) auf das gewünschte Auswahltool.  
  
2.  Bewegen Sie die Einfügemarke zu einer Ecke des Bildbereichs, den Sie markieren möchten.  Wenn sich die Einfügemarke über dem Bild befindet, wird ein Fadenkreuz angezeigt.  
  
3.  Ziehen Sie die Einfügemarke zur gegenüberliegenden Ecke des Bereichs, den Sie markieren möchten.  Ein Rechteck zeigt an, welche Pixel markiert werden.  Alle Pixel innerhalb des Rechtecks, einschließlich der darunter liegenden Pixel, werden in die Markierung einbezogen.  
  
4.  Lassen Sie die Maustaste los.  Der Markierungsrahmen umschließt den markierten Bereich.  
  
### So markieren Sie ein ganzes Bild  
  
1.  Klicken Sie außerhalb der aktuellen Markierung auf das Bild.  Der Fokus des Markierungsrahmens wird verlagert, sodass erneut das gesamte Bild umschlossen ist.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)