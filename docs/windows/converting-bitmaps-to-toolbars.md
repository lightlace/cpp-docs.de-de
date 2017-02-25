---
title: "Converting Bitmaps to Toolbars | Microsoft Docs"
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
  - "bitmaps [C++], converting to toolbars"
  - "Toolbar editor, converting bitmaps"
  - "toolbars [C++], converting bitmaps"
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Converting Bitmaps to Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch Konvertierung einer Bitmap kann eine neue Symbolleiste erstellt werden.  Die Grafik der Bitmap wird in die Schaltflächenbilder für eine Symbolleiste konvertiert.  Normalerweise enthält eine einzelne Bitmap mehrere Schaltflächenbilder, die jeweils ein Symbol pro Schaltfläche darstellen.  Die Bilder können eine beliebige Größe aufweisen; in der Standardeinstellung hat das Bild eine Breite und Höhe von 16 Pixel.  Die Größe der Schaltflächenbilder kann im [Dialogfeld "Neue Symbolleistenressource"](../mfc/new-toolbar-resource-dialog-box.md) festgelegt werden, wenn Sie den Befehl **Symbolleisten\-Editor** im Menü **Bild** des Grafik\-Editors auswählen.  
  
### So konvertieren Sie Bitmaps in eine Symbolleiste  
  
1.  Öffnen Sie eine vorhandene Bitmapressource im [Grafik\-Editor](../mfc/image-editor-for-icons.md).  \(Falls die Bitmap noch nicht in der RC\-Datei enthalten ist, klicken Sie mit der rechten Maustaste auf die RC\-Datei, wählen im Kontextmenü die Option **Importieren**, navigieren zu der Bitmap, die der RC\-Datei hinzugefügt werden soll, und klicken dann auf **Öffnen**.\)  
  
2.  Wählen Sie im Menü **Bild** den Befehl **Symbolleisten\-Editor**.  
  
     Das [Dialogfeld "Neue Symbolleistenressource"](../mfc/new-toolbar-resource-dialog-box.md) wird geöffnet.  Sie können die Breite und Höhe der Symbolbilder ändern, um sie an die Bitmap anzupassen.  Das Symbolleistenbild wird anschließend im Symbolleisten\-Editor angezeigt.  
  
3.  Um die Konvertierung zu beenden, ändern Sie die Befehls\-ID der Schaltfläche im [Eigenschaftenfenster](../Topic/Properties%20Window.md).  Geben Sie die neue ID ein, oder wählen Sie eine ID aus der Dropdownliste aus.  
  
    > [!TIP]
    >  In der Titelleiste des Eigenschaftenfensters befindet sich eine Schaltfläche in Form einer Heftzwecke.  Durch Klicken auf diese Schaltfläche wird die Funktion **Automatisch im Hintergrund** für das Fenster aktiviert bzw. deaktiviert.  Um schnell alle Eigenschaften der Symbolleisten\-Schaltflächen zu durchlaufen, ohne einzelne Eigenschaftenfenster erneut öffnen zu müssen, deaktivieren Sie **Automatisch im Hintergrund**, sodass das Eigenschaftenfenster geöffnet bleibt.  
  
 Sie können die Befehls\-IDs der Schaltflächen auch auf der neuen Symbolleiste ändern, indem Sie das [Eigenschaftenfenster](../Topic/Properties%20Window.md) verwenden.  Informationen über das Bearbeiten der neuen Symbolleiste finden Sie unter [Erstellen, Verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../mfc/creating-moving-and-editing-toolbar-buttons.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 MFC oder ATL  
  
## Siehe auch  
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)