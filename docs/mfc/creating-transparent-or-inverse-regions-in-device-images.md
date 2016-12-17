---
title: "Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], screen regions"
  - "inverse colors, device images"
  - "transparent regions, device images"
  - "transparency, device images"
  - "Image editor [C++], device images"
  - "inverse regions, device images"
  - "cursors [C++], transparent regions"
  - "screen colors"
  - "regions, transparent"
  - "icons [C++], transparent regions"
  - "display devices, transparent and screen regions"
  - "transparent regions in devices"
  - "regions, inverse"
  - "colors [C++], Image editor"
  - "device projects, transparent images"
  - "icons [C++], screen regions"
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im [Grafik\-Editor](../mfc/image-editor-for-icons.md) besitzen Symbol\- oder Cursorbilder zunächst das Attribut "transparent".  Obwohl Symbol\- und Cursorbilder eigentlich rechteckig sind, werden viele nicht in dieser Form angezeigt, da bestimmte Teile transparent sind; an diesen Stellen bleibt der Bildschirm unter dem Symbol oder Cursor sichtbar.  Wenn Sie ein Symbol ziehen, können Teile des Bildes mit invertierten Farben angezeigt werden.  Diesen Effekt erzielen Sie, indem Sie im [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md) die Einstellungen für Fensterfarbe und inverse Farbe festlegen.  
  
 Die Fensterfarben und inversen Farben, die Sie Symbolen und Cursorn zuweisen, bestimmen Form und Farbe des abgeleiteten Bildes bzw. geben die inversen Bereiche an.  Die Farben kennzeichnen jeweils die Teile des Bildes, die die entsprechenden Attribute besitzen.  Welche Farben beim Bearbeiten die Attribute für die Fensterfarbe und inverse Farbe darstellen, können Sie bei Bedarf ändern.  Diese Änderungen wirken sich nicht auf das Erscheinungsbild des Symbols oder Cursors in der Anwendung aus.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](assetId:///22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie transparente oder inverse Bereiche  
  
1.  Klicken Sie im Fenster **Farben** auf die Auswahl für **Fensterfarben** bzw. **inverse Farben**.  
  
2.  Wenden Sie die Fensterfarben oder inversen Farben mit einem Zeichentool auf das Bild an.  Weitere Informationen zu Zeichentools finden Sie unter [Using a Drawing Tool](../mfc/using-a-drawing-tool-image-editor-for-icons.md).  
  
### So ändern Sie die Fensterfarbe oder inverse Farbe  
  
1.  Klicken Sie auf die Auswahl für Fensterfarben bzw. inverse Farben.  
  
2.  Wählen Sie im Fenster **Farben** aus der Farbpalette eine Farbe aus.  
  
     Für die andere Farbauswahl wird automatisch die Komplementärfarbe festgelegt.  
  
    > [!TIP]
    >  Wenn Sie auf die Auswahl für Fensterfarbe bzw. inverse Farbe doppelklicken, wird das [Dialogfeld "Benutzerdefinierte Farbauswahl"](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) angezeigt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)