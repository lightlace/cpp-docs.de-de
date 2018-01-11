---
title: "Zugriffstasten (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs: C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c992ed83f5c86fdd770bda8f9970ff98a90c2722
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-keys-image-editor-for-icons"></a>Zugriffstasten (Bildbearbeitung für Symbole)
Im folgenden sind die Zugriffstasten für den Bild-Editor-Befehle, die Schlüssel standardmäßig gebunden sind. Um Zugriffstasten zu ändern, klicken Sie auf **Optionen** auf die **Tools** Menü, und wählen Sie dann **Tastatur** unter der **Umgebung** Ordner. Weitere Informationen finden Sie unter [Identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).  
  
> [!NOTE]
>  Die in einem Dialogfeld verfügbaren Optionen sowie die Namen und Positionen der angezeigten Menübefehle können sich je nach den persönlichen aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Optionen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
|Befehl|Tasten|Beschreibung|  
|-------------|----------|-----------------|  
|Image.AirBrushTool|STRG + A|Zeichnet einen Airbrusheffekt mit der ausgewählten Größe und Farbe.|  
|Image.BrushTool|STRG + B|Zeichnet einen Pinsel mit der ausgewählten Form, Größe und Farbe.|  
|Image.CopyAndOutlineSelection|STRG + UMSCHALT + U|Erstellt eine Kopie der aktuellen Auswahl und versieht sie mit einer Umrisslinie. Wenn die Hintergrundfarbe in der aktuellen Auswahl enthalten ist, es wird ausgeschlossen haben [transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) ausgewählten.|  
|Image.DrawOpaque|STRG + J|Stellt die aktuelle Auswahl entweder [undurchsichtig oder transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|  
|Image.EllipseTool|STRG + P|Zeichnet eine Ellipse mit der ausgewählten Zeile Breite und Farbe.|  
|Image.EraserTool|STRG + UMSCHALT + I|Löscht einen Teil des Bilds (mit der aktuellen Hintergrundfarbe).|  
|Image.FilledEllipseTool|STRG + UMSCHALT + ALT + P|Zeichnet eine ausgefüllte Ellipse.|  
|Image.FilledRectangleTool|STRG + UMSCHALT + ALT + R|Zeichnet ein ausgefülltes Rechteck.|  
|Image.FilledRoundRectangleTool|STRG + UMSCHALT + ALT + W|Zeichnet ein ausgefülltes, abgerundetes Rechteck.|  
|Image.FillTool|STRG + F|Füllt einen Bereich.|  
|Image.FlipHorizontal|STRG+H|Kippt das Bild oder die Markierung horizontal.|  
|Image.FlipVertical|UMSCHALT + ALT + H|Kippt das Bild oder die Auswahl vertikal.|  
|Image.LargerBrush|STRG + =|Erhöht die Pinselgröße in jede Richtung um ein Pixel. Um die Pinselgröße zu verringern, siehe "Image.SmallerBrush" in dieser Tabelle.|  
|Image.LineTool|STRG+L|Zeichnet eine gerade Linie von der ausgewählten Form, Größe und Farbe.|  
|Image.MagnificationTool|STRG + M|Aktiviert die **Magnify** Tool, das Ihnen ermöglicht, die bestimmte Abschnitte des Bilds zu vergrößern.|  
|Image.Magnify|STRG + UMSCHALT + M|Schaltet zwischen der aktuellen Vergrößerung und dem Vergrößerungsfaktor 1:1 um.|  
|Image.NewImageType|EINFÜGEN|Startet die [neu \<Gerät > Dialogfeld Bildtyp](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) mit dem Sie ein Bild für ein anderes Bild erstellen können.|  
|Image.NextColor|STRG +]<br /><br /> - oder -<br /><br /> STRG + NACH-RECHTS|Wechselt von der zum Zeichnen verwendeten Vordergrundfarbe zur nächsten Palettenfarbe.|  
|Image.NextRightColor|STRG + UMSCHALT +]<br /><br /> - oder -<br /><br /> UMSCHALT + STRG + NACH-RECHTS|Wechselt von der zum Zeichnen verwendeten Hintergrundfarbe zur nächsten Palettenfarbe.|  
|Image.OutlinedEllipseTool|UMSCHALT + ALT + P|Zeichnet eine ausgefüllte Ellipse mit einem Rand.|  
|Image.OutlinedRectangleTool|UMSCHALT + ALT + R|Zeichnet ein ausgefülltes Rechteck mit einem Rand.|  
|Image.OutlinedRoundRectangleTool|UMSCHALT + ALT + W|Zeichnet ein ausgefülltes, abgerundetes Rechteck mit einem Rand.|  
|Image.PencilTool|STRG + I|Zeichnet mit einem Stift von einem Pixel Breite.|  
|Image.PreviousColor|STRG + [<br /><br /> - oder -<br /><br /> STRG + NACH-LINKS|Wechselt von der zum Zeichnen verwendeten Vordergrundfarbe zur vorherigen Palettenfarbe.|  
|Image.PreviousRightColor|STRG + UMSCHALT + [<br /><br /> - oder -<br /><br /> UMSCHALT + STRG + NACH-LINKS|Wechselt von der zum Zeichnen verwendeten Hintergrundfarbe zur vorherigen Palettenfarbe.|  
|Image.RectangleSelectionTool|UMSCHALT + ALT + S|Wählt einen rechteckigen Teil des Bilds zum Verschieben, kopieren oder zu bearbeiten.|  
|Image.RectangleTool|ALT + R|Zeichnet ein Rechteck mit der ausgewählten Zeile Breite und Farbe.|  
|Image.Rotate90Degrees|STRG + UMSCHALT + H|Dreht das Bild oder die Auswahl um 90 Grad.|  
|Image.RoundedRectangleTool|ALT + W|Zeichnet ein abgerundetes Rechteck mit der ausgewählten Zeile Breite und Farbe.|  
|Image.ShowGrid|STRG + ALT + S|Schaltet die Pixelraster (aktiviert oder deaktiviert die **Pixelraster** -Option in der [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.ShowTileGrid|STRG + UMSCHALT + ALT + S|Schaltet die Kachel-Raster (aktiviert oder deaktiviert die **Kachel Raster** -Option in der [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.SmallBrush|STRG +. (Punkt)|Reduziert die **Pinsel** auf 1 Pixel. (Siehe auch "Image.LargerBrush" und "Image.SmallerBrush" in dieser Tabelle.)|  
|Image.SmallerBrush|STRG + – (minus)|Verringert die Pinselgröße in jede Richtung um ein Pixel. Um die Pinselgröße wieder zu erhöhen, siehe "Image.LargerBrush" in dieser Tabelle.|  
|Image.TextTool|STRG + T|Öffnet die [Texttool (Dialogfeld)](../windows/text-tool-dialog-box-image-editor-for-icons.md).|  
|Image.UseSelectionAsBrush|STRG + U|Zeichnet unter Verwendung der aktuellen Markierung als Pinsel.|  
|Image.ZoomIn|STRG + UMSCHALT +. (Punkt)<br /><br /> - oder -<br /><br /> STRG + NACH-OBEN|Erhöht den Vergrößerungsfaktor für die aktuelle Ansicht.|  
|Image.ZoomOut|STRG +, (Komma)<br /><br /> - oder -<br /><br /> STRG + NACH-UNTEN-TASTE|Verringert den Vergrößerungsfaktor für die aktuelle Ansicht.|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

