---
title: "Window Panes (Image Editor for Icons)"
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
  - "vc.editors.bitmap"
  - "vc.editors.icon"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "graphics editor [C++]"
  - "Image editor [C++], panes"
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Window Panes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Fenster des Grafik\-Editors zeigt ein Bild normalerweise in zwei Bereichen an, die durch eine Trennleiste getrennt sind.  Eine Ansicht zeigt die Originalgröße an und die andere eine vergrößerte Darstellung \(der Standardvergrößerungsfaktor ist 6\).  Die Ansichten in diesen beiden Fensterbereichen werden automatisch aktualisiert: Änderungen in einem Fensterbereich werden sofort auch im anderen Fensterbereich angezeigt.  Diese beiden Fensterbereiche ermöglichen Ihnen einerseits das Bearbeiten des Bildes in einer vergrößerten Ansicht, in der einzelne Pixel erkennbar sind, und andererseits die Darstellung des Bildes in Originalgröße, sodass Sie Änderungen direkt beurteilen können.  
  
 Im linken Bereich wird so viel Platz wie nötig belegt \(bis zur Hälfte des Fensters **Bild**\), um eine 1:1\-Vergrößerung \(Standard\) des Bildes anzuzeigen.  Im rechten Bereich wird das gezoomte Bild angezeigt \(mit einer standardmäßigen Vergrößerung von 6:1\).  Sie können die [Vergrößerung](../mfc/changing-the-magnification-factor-image-editor-for-icons.md) in den einzelnen Fensterbereichen ändern, indem Sie entweder das Tool **Vergrößern** auf der [Symbolleiste des Grafik\-Editors](../mfc/toolbar-image-editor-for-icons.md) oder die Zugriffstasten verwenden.  
  
 So können Sie z. B. den kleineren Bereich des Grafik\-Editor\-Fensters vergrößern und in den beiden Bereichen verschiedene Teile eines großen Bildes anzeigen.  Klicken Sie auf den Bereich, um ihn auszuwählen.  
  
 Sie können die relative Größe der Bereiche ändern, indem Sie den Mauszeiger auf dem Fensterteiler positionieren und diesen nach rechts oder links verschieben.  Wenn Sie nur in einem Bereich arbeiten möchten, kann der Fensterteiler ganz nach rechts oder links verschoben werden.  
  
 Wenn der Bereich des Grafik\-Editor\-Fensters mindestens mit dem Faktor 4 vergrößert wurde, können Sie ein [Pixelraster anzeigen](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md), das die einzelnen Pixel im Bild trennt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)