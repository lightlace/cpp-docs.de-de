---
title: "Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "image resources, display devices"
  - "icons [C++], creating"
  - "cursors [C++], types"
  - "icons [C++]"
  - "Image editor [C++], icons and cursors"
  - "cursors [C++]"
  - "display devices, creating icons for"
  - "cursors [C++], hot spots"
  - "icons [C++], types"
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Symbole und Cursor sind grafische Ressourcen, die mehrere Bilder in verschiedenen Größen und Farbschemas für verschiedene Arten von Anzeigegeräten enthalten können. Außerdem weist ein Cursor einen „Hotspot“ auf, den Ort, den Windows zum Nachverfolgen seiner Position verwendet. Sowohl Symbole als auch Cursor werden mit dem Bild\-Editor bearbeitet, wie Bitmaps und andere Bilder auch.  
  
 Wenn Sie ein neues Symbol oder einen neuen Cursor erstellen, erstellt der Bild\-Editor zunächst ein Bild eines Standardtyps. Das Bild ist anfänglich mit der Bildschirmfarbe \(transparent\) gefüllt. Wenn es sich bei dem Bild um einen Cursor handelt, befindet sich der Hotspot anfangs in der oberen linken Ecke \(Koordinaten 0,0\).  
  
 Standardmäßig unterstützt der Bild\-Editor die Erstellung weiterer Bilder für die in der folgenden Tabelle aufgelisteten Geräte. Sie können Bilder für andere Geräte erstellen, indem Sie im Dialogfeld [Benutzerdefiniertes Bild](../mfc/custom-image-dialog-box-image-editor-for-icons.md) die Parameter für Breite, Höhe und Anzahl der Farben eingeben.  
  
> [!NOTE]
>  Mit der Bildbearbeitung können Sie 32\-Bit\-Bilder anzeigen, sie aber nicht bearbeiten.  
  
|Farbe|Breite \(in Pixel\)|Höhe \(in Pixel\)|  
|-----------|-------------------------|-----------------------|  
|Monochrom|16|16|  
|Monochrom|32|32|  
|Monochrom|48|48|  
|Monochrom|64|64|  
|Monochrom|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [Erstellen eines neuen Bilds für ein Gerät \(Symbol oder Cursor\)](../mfc/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Hinzufügen eines Bildes für ein anderes Anzeigegerät](../mfc/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Kopieren eines Gerätebildes](../mfc/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Löschen eines Gerätebildes](../mfc/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [Erstellen transparenter oder invertierter Bereiche in Gerätebildern](../mfc/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [Erstellen eines Symbols oder Cursors mit 256 Farben](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [Festlegen des Hotspots eines Cursors](../mfc/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Keine  
  
## Siehe auch  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Symbole](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [Cursor](http://msdn.microsoft.com/library/windows/desktop/ms646970)