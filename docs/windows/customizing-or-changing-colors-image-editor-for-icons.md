---
title: Anpassen oder Ändern von Farben (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.customcolorselector
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
ms.openlocfilehash: 7ab353ad0aa22c74eeba58e9310d9bc0f8d5a832
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560282"
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>Anpassen oder Ändern von Farben (Bildbearbeitung für Symbole)

Die **Image** Anmerkung der Redaktion [Farben (Palette)](../windows/colors-window-image-editor-for-icons.md) werden anfänglich 16 Standardfarben angezeigt. Mit den bereits angezeigten Farben können Sie auch eigene benutzerdefinierten Farben erstellen. Sie können dann [speichern und Laden Sie eine benutzerdefinierte Farbpalette](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md).

Die **benutzerdefinierte Farbauswahl** Dialogfeld können Sie die Farben anpassen, Sie für Ihr Image verwenden. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Farbverlauf Farbanzeige**|Ändert die Werte einer ausgewählten Farbe. Positionieren Sie das Fadenkreuz, auf die Farbe, die Sie ändern möchten. Klicken Sie dann den Schieberegler nach oben oder unten, um Änderungen der Helligkeit oder RGB-Werte der Farbe.|
|**Helligkeits-Symbolleiste**|Legt die Helligkeit für die Farbe, die Sie, in Auswählen der **Farbverlauf Farbanzeige** Feld. Wählen Sie aus, und ziehen Sie den weißen Pfeil der Balken für größere Helligkeit oder nach unten bei kleiner. Die **Farbe** Feld zeigt die Farbe, die Sie ausgewählt haben und die Auswirkungen der Helligkeit, die Sie festlegen.|
|**Farbe**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Hue**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Sätt.:**|Gibt an, der Sättigungswert der Farbe, die Sie definieren. Die Sättigung ist die Menge des in einem angegebenen Farbton. Werte zwischen 0 und 240.|
|**Lum**|Listet die Brillanz (Helligkeit) der Farbe, die Sie definieren. Werte zwischen 0 und 240.|
|**Rot**|Gibt den Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Grün**|Gibt den grünen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Blau**|Gibt den blauen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|

## <a name="to-change-colors-on-the-colors-palette"></a>So ändern Sie die Farben in der Farbpalette

1. Von der **Image** Menü wählen **Farben anpassen**.

1. In der **benutzerdefinierte Farbauswahl** Dialogfeld Feld, definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben, oder wählen Sie eine Farbe in der **Farbverlauf Farbanzeige** Feld.

1. Legen Sie die Helligkeit durch Verschieben des Schiebereglers auf der **Helligkeit** Leiste.

1. Viele benutzerdefinierte Farben werden gedithert. Wenn Sie der Volltonfarbe entspricht, die der Ditheringfarbe Farbe am nächsten möchten, doppelklicken Sie auf die **Farbe** Feld.

   Wenn Sie später die geditherte Farbe angezeigt werden sollen, verschieben Sie den Schieberegler auf die **Helligkeit** Balken- oder verschieben Sie das Fadenkreuz, in der **Farbverlauf Farbanzeige** Feld erneut aus, um das dithering wiederherzustellen.

1. Wählen Sie **OK** auf die neue Farbe hinzuzufügen.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Menü "Bild"](../windows/image-menu-image-editor-for-icons.md)<br/>
[Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md)