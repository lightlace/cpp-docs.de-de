---
title: "Creating a Custom Brush (Image Editor for Icons) | Microsoft Docs"
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
  - "colors [C++], brush"
  - "brushes, colors"
  - "brushes, creating custom"
  - "images [C++], creating custom brushes"
  - "graphics [C++], custom brushes"
  - "custom brushes"
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating a Custom Brush (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein benutzerdefinierter Pinsel ist ein rechteckiger Ausschnitt eines Bildes, den Sie auswählen und wie einen vorgegebenen Pinsel des Grafik\-Editors verwenden können.  Alle Operationen, die Sie für eine Markierung durchführen können, können Sie auch für einen benutzerdefinierten Pinsel durchführen.  
  
### So erstellen Sie einen benutzerdefinierten Pinsel aus einem Bildbereich  
  
1.  [Markieren Sie den Bildbereich](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md), der für den Pinsel verwendet werden soll.  
  
2.  Halten Sie die UMSCHALTTASTE gedrückt, klicken Sie auf die Markierung, und ziehen Sie sie über das Bild.  
  
     \- oder \-  
  
3.  Klicken Sie im Menü **Bild** auf **Auswahl als Pinsel verwenden**.  
  
     Die Markierung wird zu einem benutzerdefinierten Pinsel, durch den die in der Markierung enthaltenen Farben auf das Bild verteilt werden.  Entlang dem Ziehpfad werden Kopien der Markierung abgelegt.  Je langsamer Sie ziehen, desto mehr Kopien werden erstellt.  
  
     **Hinweis** Wenn Sie auf **Auswahl als Pinsel verwenden** klicken, ohne zuerst einen Bildbereich auszuwählen, wird das gesamte Bild als Pinsel verwendet.  Der Effekt eines benutzerdefinierten Pinsels hängt außerdem davon ab, ob Sie einen [deckenden oder transparenten Hintergrund](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) ausgewählt haben.  
  
 In der Regel sind Pixel eines benutzerdefinierten Pinsels, die mit der aktuellen Hintergrundfarbe übereinstimmen, transparent: Das vorhandene Bild wird also nicht übermalt.  Sie können dieses Verhalten ändern, sodass die Pixel in der Hintergrundfarbe das vorhandene Bild übermalen.  
  
 Der benutzerdefinierte Pinsel kann wie ein Stempel oder eine Schablone verwendet werden, um eine Vielzahl von Spezialeffekten zu erzielen.  
  
#### So zeichnen Sie Formen mit einem benutzerdefinierten Pinsel in der Hintergrundfarbe  
  
1.  [Wählen Sie einen deckenden oder transparenten Hintergrund aus](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Wählen Sie als Hintergrundfarbe](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) die Farbe, in der Sie zeichnen möchten.  
  
3.  Positionieren Sie den benutzerdefinierten Pinsel an der Stelle, an der Sie zeichnen möchten.  
  
4.  Klicken Sie mit der rechten Maustaste.  Die deckenden Bereiche des benutzerdefinierten Pinsels werden in der Hintergrundfarbe gezeichnet.  
  
#### So verdoppeln oder halbieren Sie die benutzerdefinierte Pinselstärke  
  
1.  Drücken Sie die PLUSZEICHENTASTE \(**\+**\), um die Pinselstärke zu verdoppeln, oder die MINUSZEICHENTASTE \(**\-**\), um sie zu halbieren.  
  
#### So löschen Sie den benutzerdefinierten Pinsel  
  
1.  Drücken Sie ESC, oder wählen Sie ein anderes Zeichentool.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)