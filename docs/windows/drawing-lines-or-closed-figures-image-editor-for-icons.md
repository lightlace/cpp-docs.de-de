---
title: "Drawing Lines or Closed Figures (Image Editor for Icons) | Microsoft Docs"
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
  - "closed figures, drawing"
  - "lines [C++], painting"
  - "lines [C++], drawing"
  - "Image editor [C++], drawing lines"
  - "shapes, drawing"
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Drawing Lines or Closed Figures (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die im Grafik\-Editor enthaltenen Tools zum Zeichnen von Linien und geschlossenen Körpern funktionieren alle nach demselben Prinzip: Sie positionieren die Einfügemarke an einer Stelle und ziehen sie an eine andere Stelle.  Bei Linien positionieren Sie die Einfügemarke auf den Endpunkten.  Bei geschlossenen Körpern positionieren Sie sie auf den gegenüberliegenden Ecken eines Rechtecks, das den Körper begrenzt.  
  
 Die Stärke von Linien hängt vom aktuell ausgewählten Pinsel und die von Umrisslinien geschlossener Körper von der aktuell ausgewählten Stärke ab.  Linien und alle umrahmten wie auch gefüllten Körper werden in der aktuellen Vordergrundfarbe gezeichnet, wenn Sie die linke Maustaste drücken. Diese Objekte werden in der aktuellen Hintergrundfarbe gezeichnet, wenn Sie die rechte Maustaste drücken.  
  
### So zeichnen Sie eine Linie  
  
1.  Klicken Sie auf der [Symbolleiste des Grafik\-Editors](../mfc/toolbar-image-editor-for-icons.md) \(oder unter dem Befehl **Tools** im Menü **Bild**\) auf das Tool **Linie**.  
  
2.  Wählen Sie ggf. Farben und einen Pinsel aus:  
  
    -   Klicken Sie in der [Farbpalette](../windows/colors-window-image-editor-for-icons.md) mit der linken Maustaste, um eine Vordergrundfarbe auszuwählen, oder mit der rechten Maustaste, um eine Hintergrundfarbe auszuwählen.  
  
    -   Klicken Sie in der [Optionsauswahl](../mfc/toolbar-image-editor-for-icons.md) auf eine Form, die den gewünschten Pinsel darstellt.  
  
3.  Positionieren Sie den Mauszeiger auf dem Anfangspunkt der Linie.  
  
4.  Ziehen Sie den Mauszeiger auf den Endpunkt der Linie.  
  
### So zeichnen Sie einen geschlossenen Körper  
  
1.  Klicken Sie auf der Symbolleiste des Grafik\-Editors \(oder unter dem Befehl **Tools** im Menü **Bild**\) auf das Tool zum Zeichnen geschlossener Körper.  
  
     Mit den Tools zum Zeichnen geschlossener Körper erstellen Sie die Körper, die auf der jeweiligen Schaltfläche dargestellt sind.  
  
2.  Wählen Sie ggf. Farben und eine Linienstärke aus.  
  
3.  Verschieben Sie den Mauszeiger auf eine Ecke des rechteckigen Bereichs, in dem Sie den Körper zeichnen möchten.  
  
4.  Ziehen Sie den Mauszeiger zur diagonal gegenüberliegenden Ecke.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)