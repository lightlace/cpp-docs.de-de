---
title: Menü "Bild" (C++-Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
helpviewer_keywords:
- Image menu
- Grid Settings dialog box [C++]
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
ms.openlocfilehash: e7d7d92401d5910cbb8aba8ab4c6000eca45cb01
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849729"
---
# <a name="image-menu-c-image-editor-for-icons"></a>Menü "Bild" (C++-Bildbearbeitung für Symbole)

Die **Image** Menü wird, nur, wenn angezeigt die **Image** Editor aktiv ist, enthält Befehle zum Bearbeiten von Bildern, Verwalten von Farbpaletten und festlegen **Bildbearbeitung** Fenster Optionen. Darüber hinaus sind die Befehle für die Verwendung von Gerätebildern verfügbar, beim Arbeiten mit Symbolen und Cursorn.

|Befehl|Beschreibung|
|---|---|
|**Farben umkehren**|Kehrt die verwendeten Farben an. Weitere Informationen finden Sie unter [Invertieren der Farben in einer Auswahlanweisung](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).|
|**Horizontal spiegeln**|Kippt das Bild oder die Markierung horizontal. Weitere Informationen finden Sie unter [Kippen eines Bilds](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Vertikal spiegeln**|Kippt das Bild oder die Auswahl vertikal. Weitere Informationen finden Sie unter [Kippen eines Bilds](../windows/flipping-an-image-image-editor-for-icons.md).|
|**90 Grad drehen**|Dreht das Bild oder die Auswahl um 90 Grad. Weitere Informationen finden Sie unter [Kippen eines Bilds](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Anzeigen des Fensters "Farben"**|Öffnet die [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md), in dem Sie die Farben, verwenden Sie für Ihr Image auswählen können. Weitere Informationen finden Sie unter [arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md).|
|**Auswahl als Pinsel verwenden**|Ermöglicht Ihnen die Erstellung von benutzerdefinierten Pinseln aus einem Teil eines Bilds. Ihre Auswahl wird es sich um einen benutzerdefinierten Pinsel, der die Farben in der Auswahl auf das Bild verteilt. Kopien der Auswahl bleiben entlang des Pfads ziehen. Sie ziehen, desto langsamer, desto mehr Kopien erfolgen. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).|
|**Auswahl kopieren und Gliedern**|Erstellt eine Kopie der aktuellen Auswahl und versieht sie mit einer Umrisslinie. Wenn die Hintergrundfarbe in der aktuellen Auswahl enthalten ist, es wird ausgeschlossen haben [transparent](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) ausgewählten.
|**Anpassen von Farben**|Öffnet die [benutzerdefinierte Farbauswahl](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), können Sie die Farben anpassen, Sie für Ihr Image verwenden. Weitere Informationen finden Sie unter [anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md).|
|**Palette laden**|Öffnet die [Palettenfarben laden (Dialogfeld)](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), sodass Sie beim Laden von Palettenfarben, die zuvor in einer PAL-Datei gespeichert.|
|**Palette speichern**|Die Palettenfarben speichert einer PAL-Datei.|
|**Deckend zeichnen**|Bei Auswahl dieser Option wird die aktuelle Auswahl nicht transparent. Wenn diese Option deaktiviert ist, wird die aktuelle Auswahl transparent. Weitere Informationen finden Sie unter [auswählen, einen transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|**Symbolleisten-Editor**|Öffnet die [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md).|
|**Rastereinstellungen**|Öffnet die **Rastereinstellungen** Dialogfeld, in dem Sie Raster für das Image angeben können.|
|**Neuer Bildtyp**|Öffnet die [neu \<Gerät > Bildtyp (Dialogfeld)](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md). Eine einzelnes Symbol-Ressource kann mehrere Images mit verschiedenen Größen enthalten, und Windows können der Größe der entsprechenden Symbole je nachdem, wie sich das alles angezeigt werden soll. Ein neuer Gerätetyp nicht ändert die Größe des Symbols, aber stattdessen erstellt ein neues Image innerhalb des Symbols. Gilt nur für Symbole und Cursor.|
|**Aktuelle Symbol/Cursorbildtyp**|Öffnet ein Untermenü, in der ersten verfügbaren Cursor oder ein Symbol-Images (die ersten neun) aufgeführt. Klicken Sie im Untermenü mit dem letzten Befehl **mehr...** , öffnet der [öffnen \<Gerät > Bild (Dialogfeld)](../windows/open-device-image-dialog-box-image-editor-for-icons.md).|
|**Bildtyp löschen**|Löscht das Image des ausgewählten Geräts an.|
|**Extras**|Öffnet ein Untermenü, das alle verfügbaren aus Tools enthält die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md).|

Die **Rastereinstellungen** Dialogfeld können Sie die Einstellungen für das Image angeben und Gitternetzlinien angezeigt, auf das Bild bearbeitet. Die Zeilen sind nützlich für das Abbild zu bearbeiten, aber nicht als Teil des Bilds selbst gespeichert.

|Eigenschaft|Beschreibung|
|---|---|
|**Pixelraster**|Dieses Kontrollkästchen aktiviert, wird ein Raster aus, um die einzelnen Pixel in der Grafik-Editor angezeigt. Das Raster, die nur auf 4 × und höherer Auflösung angezeigt wird.|
|**Linienraster**|Bei Auswahl dieser Option zeigt ein Raster aus, um Blöcke von Pixeln, des Grafik-Editors, die durch die Werte der Raster-Abstand angegeben.|
|**Width**|Gibt die Breite jedes Blocks Kachel. Diese Eigenschaft ist nützlich, beim Zeichnen von Bitmaps, enthält mehrere Images, die in regelmäßigen Abständen angeordnet sind.|
|**Height**|Gibt die Höhe jedes Blocks Kachel. Diese Eigenschaft ist nützlich, beim Zeichnen von Bitmaps, enthält mehrere Images, die in regelmäßigen Abständen angeordnet sind.|

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Größenänderungen bei Bildern](../windows/resizing-an-image-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)