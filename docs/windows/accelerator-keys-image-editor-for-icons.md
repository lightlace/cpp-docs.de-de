---
title: Zugriffstasten (Bildbearbeitung für Symbole C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
ms.openlocfilehash: 062b860849d968e18657afb66b568a1bf6f2b6d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505104"
---
# <a name="accelerator-keys-c-image-editor-for-icons"></a>Zugriffstasten (Bildbearbeitung für Symbole C++)

Unten sind die Zugriffstasten für den Bild-Editor-Befehlen, die standardmäßig auf Schlüssel gebunden sind. Um Zugriffstasten zu ändern, klicken Sie auf **Optionen** auf die **Tools** Menü, und wählen Sie dann **Tastatur** unter der **Umgebung** Ordner. Weitere Informationen finden Sie unter [Identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> Die in einem Dialogfeld verfügbaren Optionen sowie die Namen und Positionen der angezeigten Menübefehle können sich je nach den persönlichen aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Optionen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

|Befehl|Tasten|Beschreibung|
|-------------|----------|-----------------|
|Image.AirBrushTool|**STRG** + **A**|Zeichnet einen Airbrusheffekt mit der ausgewählten Größe und Farbe.|
|Image.BrushTool|**STRG** + **B**|Zeichnet mit einem Pinsel der ausgewählten Form, Größe und Farbe.|
|Image.CopyAndOutlineSelection|**STRG** + **UMSCHALT** + **U**|Erstellt eine Kopie der aktuellen Auswahl und versieht sie mit einer Umrisslinie. Wenn die Hintergrundfarbe in der aktuellen Auswahl enthalten ist, es wird ausgeschlossen werden, wenn man [transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) ausgewählten.|
|Image.DrawOpaque|**STRG** + **J**|Stellt die aktuelle Auswahl entweder [undurchsichtig oder durchsichtig](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|Image.EllipseTool|**STRG** + **P**|Zeichnet eine Ellipse mit der ausgewählten Linienstärke und Farbe.|
|Image.EraserTool|**STRG** + **UMSCHALT** + **I**|Löscht einen Teil des Bilds (mit der aktuellen Hintergrundfarbe).|
|Image.FilledEllipseTool|**STRG** + **UMSCHALT** + **Alt** + **P**|Zeichnet eine ausgefüllte Ellipse.|
|Image.FilledRectangleTool|**STRG** + **UMSCHALT** + **Alt** + **R**|Zeichnet ein ausgefülltes Rechteck.|
|Image.FilledRoundRectangleTool|**STRG** + **UMSCHALT** + **Alt** + **W**|Zeichnet ein ausgefülltes, abgerundetes Rechteck.|
|Image.FillTool|**STRG** + **F**|Füllt einen Bereich.|
|Image.FlipHorizontal|**STRG** + **H**|Kippt das Bild oder die Markierung horizontal.|
|Image.FlipVertical|**UMSCHALT**+ **Alt** + **H**|Kippt das Bild oder die Auswahl vertikal.|
|Image.LargerBrush|**STRG** + **=**|Erhöht die Pinselgröße in jede Richtung um ein Pixel. Um die Pinselgröße zu verringern, siehe "Image.SmallerBrush" in dieser Tabelle.|
|Image.LineTool|**STRG** + **L**|Zeichnet eine gerade Linie von der ausgewählten Form, Größe und Farbe.|
|Image.MagnificationTool|**STRG** + **M**|Aktiviert die **Magnify** -Tool, das Ihnen ermöglicht, bestimmte Abschnitte Ihres Images vergrößern.|
|Image.Magnify|**STRG** + **UMSCHALT** + **M**|Schaltet zwischen der aktuellen Vergrößerung und dem Vergrößerungsfaktor 1:1 um.|
|Image.NewImageType|**Einfügen**|Startet die [neu \<Gerät > Bildtyp (Dialogfeld)](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) mit dem Sie ein Image für einen anderen Bildtyp erstellen können.|
|Image.NextColor|**STRG** + **]**<br /><br /> - oder -<br /><br /> **STRG** + **-rechts-Taste**|Wechselt von der zum Zeichnen verwendeten Vordergrundfarbe zur nächsten Palettenfarbe.|
|Image.NextRightColor|**STRG** + **UMSCHALTTASTE** + **]**<br /><br /> - oder -<br /><br /> **UMSCHALT** + **STRG** + **-rechts-Taste**|Wechselt von der zum Zeichnen verwendeten Hintergrundfarbe zur nächsten Palettenfarbe.|
|Image.OutlinedEllipseTool|**UMSCHALT** + **Alt** + **P**|Zeichnet eine ausgefüllte Ellipse mit einem Rand.|
|Image.OutlinedRectangleTool|**UMSCHALT** + **Alt** + **R**|Zeichnet ein ausgefülltes Rechteck mit einem Rand.|
|Image.OutlinedRoundRectangleTool|**UMSCHALT** + **Alt** + **W**|Zeichnet ein ausgefülltes, abgerundetes Rechteck mit einem Rand.|
|Image.PencilTool|**STRG** + **I**|Zeichnet mit einem Stift von einem Pixel Breite.|
|Image.PreviousColor|**STRG** + **[**<br /><br /> - oder -<br /><br /> **STRG** + **Pfeil nach links**|Wechselt von der zum Zeichnen verwendeten Vordergrundfarbe zur vorherigen Palettenfarbe.|
|Image.PreviousRightColor|**STRG** + **UMSCHALTTASTE** + **[**<br /><br /> - oder -<br /><br /> **UMSCHALT** + **STRG** + **Pfeil nach links**|Wechselt von der zum Zeichnen verwendeten Hintergrundfarbe zur vorherigen Palettenfarbe.|
|Image.RectangleSelectionTool|**UMSCHALT** + **Alt** + **S**|Wählt einen rechteckigen Bereich des Bildes zum Verschieben, kopieren oder zu bearbeiten.|
|Image.RectangleTool|ALT + R|Zeichnet ein Rechteck mit der ausgewählten Linienstärke und Farbe.|
|Image.Rotate90Degrees|**STRG** + **UMSCHALT** + **H**|Dreht das Bild oder die Auswahl um 90 Grad.|
|Image.RoundedRectangleTool|**ALT** + **W**|Zeichnet ein abgerundetes Rechteck mit der ausgewählten Linienstärke und Farbe.|
|Image.ShowGrid|**STRG** + **Alt** + **S**|Schaltet die pixelrasteroption (aktiviert oder deaktiviert die **Pixelraster** option die [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.ShowTileGrid|**STRG** + **UMSCHALT** + **Alt** + **S**|Schaltet die grobrasteroption um (aktiviert oder deaktiviert die **Grobraster** option die [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.SmallBrush|**STRG** + **.** (Punkt)|Reduziert die **Pinsel** auf 1 Pixel. (Siehe auch "Image.LargerBrush" und "Image.SmallerBrush" in dieser Tabelle.)|
|Image.SmallerBrush|**STRG**  +  **-** (minus)|Verringert die Pinselgröße in jede Richtung um ein Pixel. Um die Pinselgröße wieder zu erhöhen, siehe "Image.LargerBrush" in dieser Tabelle.|
|Image.TextTool|**STRG** + **T**|Öffnet die [Text Texttool (Dialogfeld)](../windows/text-tool-dialog-box-image-editor-for-icons.md).|
|Image.UseSelectionAsBrush|**STRG** + **U**|Zeichnet unter Verwendung der aktuellen Markierung als Pinsel.|
|Image.ZoomIn|**STRG** + **UMSCHALT** + **.** (Punkt)<br /><br /> - oder -<br /><br /> **STRG** + **Pfeil nach oben**|Erhöht den Vergrößerungsfaktor für die aktuelle Ansicht.|
|Image.ZoomOut|**STRG** + **,** (Komma)<br /><br /> - oder -<br /><br /> **STRG** + **nach unten zeigenden Pfeil**|Verringert den Vergrößerungsfaktor für die aktuelle Ansicht.|

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)