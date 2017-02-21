---
title: "Working with Color (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], background colors"
  - "Image editor [C++], Colors Palette"
  - "colors [C++], image"
  - "Colors Palette, Image editor"
  - "palettes, Image editor colors"
  - "foreground colors, Image editor"
  - "colors [C++]"
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Working with Color (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Grafik\-Editor enthält viele Features für die Verwendung und Anpassung von Farben.  Sie können eine Vordergrund\- oder Hintergrundfarbe festlegen, begrenzte Bereiche mit Farbe füllen oder eine Farbe des Bildes als aktuelle Vordergrund\- oder Hintergrundfarbe auswählen.  Die Tools auf der [Symbolleiste des Grafik\-Editors](../mfc/toolbar-image-editor-for-icons.md) können zusammen mit der Farbpalette im [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md) verwendet werden, um Bilder zu erstellen.  
  
 Alle Farben – sowohl für Schwarzweißbilder als auch für Bilder mit 16 Farben – werden im Fenster **Farben** in der Farbpalette angezeigt.  Zusätzlich zu den 16 Standardfarben können Sie eigene, benutzerdefinierte Farben erstellen.  Wenn Sie eine der Farben in der Palette ändern, wird sofort auch die entsprechende Farbe im Bild geändert.  
  
 Zur Bearbeitung von Symbol\- und Cursorbildern mit 256 Farben wird die Eigenschaft **Farben** im [Eigenschaftenfenster](../Topic/Properties%20Window.md) verwendet.  Weitere Informationen finden Sie unter [Erstellen eines Symbols oder Cursors mit 256 Farben](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Mit dem Bild\-Editor können Sie 32\-Bit\-Bilder anzeigen, aber nicht bearbeiten.  
  
 Außerdem können Echtfarbbilder erstellt werden.  Echtfarbmuster werden jedoch nicht in der vollständigen Palette im Fenster **Farben** angezeigt, sondern nur im Anzeigebereich für die Vordergrund\- oder Hintergrundfarbe.  Echtfarben werden im [Dialogfeld "Benutzerdefinierte Farbauswahl"](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) erstellt.  Weitere Informationen finden Sie unter [Anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Benutzerdefinierte Farbpaletten können auf einem Datenträger gespeichert und bei Bedarf neu geladen werden.  Die zuletzt verwendete Farbpalette wird in der Registrierung gespeichert und automatisch geladen, wenn Sie Visual Studio das nächste Mal starten.  
  
-   [Auswählen von Vordergrund\- oder Hintergrundfarben](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Füllen von begrenzten Bereichen eines Bildes mit einer Farbe](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Übertragen einer Farbe eines Bildes auf andere Elemente](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Auswählen eines transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Invertieren der Farben in einer Markierung](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Speichern und Laden von verschiedenen Farbpaletten](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Fensterfarben](../windows/colors-window-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Ressourcen](_win32_Resources)