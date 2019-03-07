---
title: 'Vorgehensweise: Arbeiten mit Farben'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.color
- vc.editors.customcolorselector
- vc.editors.loadcolorpalette
- vc.editors.colorswindow
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
- Image editor [C++], colors
- colors [C++], Image editor
- colors [C++], image
- images [C++], colors
- Image editor [C++], colors
- Fill tool
- colors [C++], image
- images [C++], colors
- colors [C++], selection tools
- Image editor [C++], colors
- Select Color tool
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
- Image editor [C++], Colors Palette
- Colors Palette, Image editor
- colors [C++], inverting
- colors [C++]
- Color Indicator
- colors [C++], Colors window
- Colors window, hiding colors
- Show Colors Window command
- Colors window, displaying colors
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
- colors [C++], image
- Image editor [C++], color inversion
- images [C++], colors
- colors [C++], inverting
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: f50d734ab35968aa107e23b8450d60f316b6002e
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563146"
---
# <a name="how-to-work-with-color"></a>Vorgehensweise: Arbeiten mit Farben

Die **Bildbearbeitung** enthält viele Features, die speziell behandelt und Anpassen von Farben. Sie können eine Vorder- oder Hintergrund Farbe festlegen, füllen von begrenzten Bereichen mit Farbe oder eine andere Farbe auf ein Bild, als die aktuelle Vorder- oder Hintergrund Farbe auswählen. Sie können die Tools verwenden, auf die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) zusammen mit den Farben (Palette) in der **Farben** um Images zu erstellen.

Alle Farben für Monochrom und 16 Farben-Images werden angezeigt, der **Farben** Palette in der **Farben** Fenster. Zusammen mit 16 Standardfarben können Sie eigene benutzerdefinierten Farben erstellen. Ändern der Farben in der Palette ändert sich sofort auf die entsprechende Farbe im Bild aus.

Beim Arbeiten mit 256-Farben-Symbol und der Cursor-Images, die **Farben** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) verwendet wird. Weitere Informationen finden Sie unter [Erstellen eines 256-Farben-Symbols oder Cursors](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).

True Color-Bilder können auch erstellt werden. Jedoch nicht "true" Farbmuster angezeigt, in der vollständigen Palette in der **Farben** Fenster; sie werden nur in den Vorder- oder Hintergrund Indikator Farbbereich. "True" Farben werden erstellt, mit der **benutzerdefinierte Farbauswahl** Dialogfeld.

Sie können benutzerdefinierte Farbpaletten auf Datenträger speichern und erneut geladen werden, je nach Bedarf. Die zuletzt verwendeten Farben-Palette ist in der Registrierung gespeichert und beim nächsten start von Visual Studio automatisch geladen.

Die **Farben** Fenster besteht aus zwei Teilen:

- Die **Farben (Palette)**, dies ist ein Array der farbbeispiele, die Farben darstellen können. Sie können die Beispiele, Vordergrund- und Hintergrundfarben auszuwählen, wenn Sie die Grafiktools verwenden auswählen.

- Die **Farbanzeige**, zeigt die Vordergrund- und Hintergrundfarben und Selektoren für die Bildschirm- und invertierte Farbe.

   ![Fenster "Farben"](../windows/media/vccolorswindow.gif "VcColorsWindow")<br/>
   **Farben** Fenster

> [!NOTE]
> Die **Bildschirm Farbe** und **invertierte Farbe** Tools sind nur verfügbar für Symbole und Cursor.

Sie können die **Farben** -Fenster mit der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md).

- Zum Anzeigen der **Farben** Fenster mit der rechten Maustaste in ein **Bild-Editor** Bereich, und wählen Sie **Fenster "Farben" anzeigen**, oder wechseln Sie zum Menü [Image](../windows/image-menu-image-editor-for-icons.md)  >  **Anzeigen des Fensters "Farben"**.

- So blenden Sie aus der **Farben** Fenster lösen Sie das Fenster (diese Aktion ermöglicht das Fenster automatisch ausgeblendet, wenn er nicht verwendet wird), oder wählen die **schließen** Schaltfläche.

Die **Farben** Palette werden anfänglich 16 Standardfarben angezeigt. Mit den bereits angezeigten Farben können Sie auch eigene benutzerdefinierten Farben erstellen. Sie können dann speichern und Laden eine benutzerdefinierte Farbpalette.

Die **benutzerdefinierte Farbauswahl** Dialogfeld können Sie die Farben anpassen, Sie für Ihr Image mit den folgenden Eigenschaften verwenden:

|Eigenschaft|Beschreibung|
|--------------------------|--------------------------|
|**Farbverlauf Farbanzeige**|Ändert die Werte einer ausgewählten Farbe.<br/><br/>Positionieren Sie das Fadenkreuz, auf die Farbe, die Sie verwenden möchten, ändern und den Schieberegler nach oben oder unten auf die Brillanz oder RGB-Werte der Farbe zu ändern.|
|**Helligkeits-Symbolleiste**|Legt die Helligkeit für die Farbe, die Sie, in Auswählen der **Farbverlauf Farbanzeige** Feld.<br/><br/>Wählen Sie aus, und ziehen Sie den weißen Pfeil der Balken für größere Helligkeit oder nach unten bei kleiner. Die **Farbe** Feld zeigt die Farbe, die Sie ausgewählt haben und die Auswirkungen der Helligkeit, die Sie festlegen.|
|**Farbe**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Hue**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Sätt.:**|Gibt an, der Sättigungswert der Farbe, die Sie definieren. Die Sättigung ist die Menge des in einem angegebenen Farbton. Werte zwischen 0 und 240.|
|**Lum**|Listet die Brillanz (Helligkeit) der Farbe, die Sie definieren. Werte zwischen 0 und 240.|
|**Rot**|Gibt den Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Grün**|Gibt den grünen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Blau**|Gibt den blauen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|

Sie können das Speichern und Laden eine **Farben** Palette mit benutzerdefinierten Farben an. In der Standardeinstellung die **Farben** zuletzt verwendete Farbpalette wird automatisch geladen, wenn Sie Visual Studio starten.

> [!TIP]
> Da die **Bildbearbeitung** hat keine Möglichkeit zum Wiederherstellen der standardmäßigen **Farben** Palette, speichern Sie die Standardeinstellung **Farben** unter einem Namen wie z. B.  *Standard.PAL* oder *default.pal* , damit Sie die Standardeinstellungen problemlos wiederherstellen können.

Verwenden Sie die **Palettenfarben laden** Dialogfeld beim Laden von speziellen Farbpaletten, die für die Verwendung in Ihrem C++-Projekt mit folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|-----------------|-----------------|
|**Suchen in**|Gibt den Speicherort einer Datei oder eines Ordners gefunden werden sollen.<br/><br/>Wählen Sie den Pfeil, um einen anderen Speicherort auswählen, oder wählen Sie das Ordnersymbol auf der Symbolleiste können Sie Ebenen zu verschieben.|
|**Dateiname**|Dient zur Eingabe der Name der Datei, die Sie öffnen möchten.<br/><br/>Um schnell eine Datei zu suchen, die Sie zuvor erstellt haben, wählen Sie den Dateinamen in der Dropdown-Liste, sofern verfügbar.<br/><br/>Wenn Sie für eine Datei durchsuchen, können Sie Sternchen (*) als Platzhalter verwenden. Sie können z. B. eingeben \*.\* um eine Liste aller Dateien anzuzeigen. Sie können auch den vollständigen Pfad einer Datei eingeben, z. B. *C:\My Documents\MyColorPalette.pal* oder  *\\\NetworkServer\MyFolder\MyColorPalette.pal*.|
|**Dateityp**|Listet die Typen der anzuzeigenden Dateien.<br/><br/>Palette (*. PAL) ist der Standardtyp für die Datei für Farbpaletten.|

## <a name="how-to"></a>Gewusst wie

### <a name="to-select-foreground-or-background-colors"></a>Auswählen von Vordergrund-oder Hintergrundfarben

Mit Ausnahme der **Radierer**, tools auf die **Bildbearbeitung** Symbolleiste Zeichnen-Befehl in der aktuellen Vordergrund- oder Hintergrundfarbe, wenn Sie die linke oder rechte Maustaste drücken.

- Wählen Sie eine Vordergrundfarbe, mit der linken Maustaste, wählen Sie die gewünschte Farbe auf den **Farben** Palette.

- Wählen Sie eine Hintergrundfarbe, mit der rechten Maustaste, wählen Sie die gewünschte Farbe auf den **Farben** Palette.

### <a name="to-fill-a-bounded-area-of-an-image-with-a-color"></a>Zum Füllen von begrenzten Bereichen eines Bilds mit einer Farbe

Die **Bildbearbeitung** bietet die **füllen** Tool für das Füllen alle Bildbereiche mit der aktuellen zeichnen oder die aktuelle Hintergrundfarbe.

### <a name="to-use-the-fill-tool"></a>Um das Füllwerkzeug verwenden

1. Verwenden der **Bildbearbeitung** Symbolleiste oder wechseln Sie zum Menü **Image** > **Tools** , und wählen Sie die **füllen** Tool.

1. Wählen Sie ggf. die Farben zu zeichnen. In der [Farben (Palette)](../windows/colors-window-image-editor-for-icons.md), wählen Sie die linke Maustaste gedrückt, wählen Sie eine Vordergrundfarbe oder der rechten Maustaste auf eine Hintergrundfarbe auswählen.

1. Verschieben der **Füllung** Tool, um den Bereich, die Sie füllen möchten.

1. Wählen Sie die linke oder rechte Maustaste-Schaltfläche bzw. mit der Vordergrund- oder die Hintergrundfarbe zu füllen.

### <a name="to-pick-up-a-color-from-an-image-to-use-elsewhere"></a>Um eine Farbe aus einem Image zu übernehmen, mit einer anderen Stelle

Die **Farbe auswählen**, oder verwandelt, Tool macht eine beliebige Farbe auf das Bild der aktuellen Vordergrund- oder Hintergrundfarbe, je nachdem, ob Sie links oder die rechte Maustaste drücken. Zum Abbrechen der **Farbe auswählen** tool, und wählen Sie ein anderes Tool.

1. Verwenden der **Bildbearbeitung** Symbolleiste oder wechseln Sie zum Menü **Image** > **Tools** , und wählen Sie die **Farbe auswählen** Tool.

1. Wählen Sie die Farbe, die Sie aus dem Image übernehmen möchten.

   > [!NOTE]
   > Nachdem Sie eine Farbe aus, übernehmen die **Bildbearbeitung** Datencenter erneut funktionsfähig, die zuletzt verwendete Tool.

1. Verwenden die linke Maustaste gedrückt für die Vordergrundfarbe darstellt, oder die rechte Maustaste der Hintergrundfarbe gezeichnet werden soll.

### <a name="to-choose-the-background"></a>Wählen Sie den Hintergrund

Beim Verschieben oder kopieren eine Auswahl aus einem Image, alle Pixel in der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen, sind standardmäßig transparent, und sie nicht am Zielspeicherort Pixel verdecken.

Sie können über einen transparenten Hintergrund (Standard) wechseln, um ein nicht transparenter Hintergrund und wieder zurück. Wenn Sie eine Auswahltool verwenden, die **transparenten Hintergrund** und **nicht transparenter Hintergrund** Optionen angezeigt, der **Option** -Selektor auf die **Bildbearbeitung** Symbolleiste.

![Optionen im Hintergrund &#45; undurchsichtig oder durchsichtig](../windows/media/vcimageeditoropaqtranspback.gif "Optionen im Hintergrund &#45; undurchsichtig oder durchsichtig")<br/>
**Transparente und undurchsichtige Optionen** auf die **Symbolleiste der Bildbearbeitung**

#### <a name="to-switch-between-a-transparent-and-opaque-background"></a>So wechseln Sie zwischen einem transparente und undurchsichtige-Hintergrund

In der **Bildbearbeitung** -Symbolleiste auf die **Option** Auswahl, und wählen Sie dann den entsprechenden Hintergrund:

- **Nicht transparenter Hintergrund (O)**: Vorhandene Bild wird von allen Bereichen der Auswahl verdeckt.

- **Transparenter Hintergrund (T)**: Vorhandenes Bild zeigt Teile der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen.

> [!TIP]
> Für eine Verknüpfung auf die **Image** Menü aktivieren oder deaktivieren Sie **Deckend zeichnen**.

Sie können die Farbe des Hintergrunds ändern, während eine Auswahl bereits aktiv ist ändern, welche Teile des Bilds transparent sind.

### <a name="to-invert-the-colors-in-a-selection"></a>Um die Farben in einer Auswahl umkehren

Die **Bildbearbeitung** bietet eine bequeme Möglichkeit zum Invertieren von Farben im ausgewählten Teil des Bilds, sodass Sie erkennen können, wie ein Bild mit invertierten Farben aussieht.

Um die Farben in der aktuellen Auswahl umkehren möchten, wechseln Sie zum Menü **Image** > **Farben umkehren**.

### <a name="to-customize-or-change-colors-on-the-colors-palette"></a>Zum Anpassen oder Ändern der Farben auf die Farben (Palette)

1. Wechseln Sie zum Menü **Image** > **Farben anpassen**.

1. In der **benutzerdefinierte Farbauswahl** Dialogfeld Feld, definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben, oder wählen Sie eine Farbe in der **Farbverlauf Farbanzeige** Feld.

1. Legen Sie die Helligkeit durch Verschieben des Schiebereglers auf der **Helligkeit** Leiste.

1. Viele benutzerdefinierte Farben werden gedithert. Wenn Sie der Volltonfarbe entspricht, die der Ditheringfarbe Farbe am nächsten möchten, doppelklicken Sie auf die **Farbe** Feld.

   Wenn Sie später die geditherte Farbe angezeigt werden sollen, verschieben Sie den Schieberegler auf die **Helligkeit** Balken- oder verschieben Sie das Fadenkreuz, in der **Farbverlauf Farbanzeige** Feld erneut aus, um das dithering wiederherzustellen.

1. Wählen Sie **OK** auf die neue Farbe hinzuzufügen.

### <a name="to-save-a-custom-colors-palette"></a>So speichern Sie eine benutzerdefinierte Farbpalette

1. Wechseln Sie zum Menü **Image** > **Palette speichern**.

1. Navigieren Sie zu dem Verzeichnis, in dem Sie die Farbpalette speichern möchten, und geben Sie einen Namen für die Palette ein.

1. Klicken Sie auf **Speichern**.

### <a name="to-load-a-custom-colors-palette"></a>So laden Sie eine benutzerdefinierte Farbpalette

1. Wechseln Sie zum Menü **Image** > **Palette laden**.

1. In der **Palettenfarben laden** Dialogfeld Feld, navigieren Sie zum richtigen Verzeichnis aus, und wählen Sie die Palette, die Sie laden möchten. **Farbe** Paletten werden mit der Erweiterung. PAL gespeichert.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
[Vorgehensweise: Erstellen eines Symbols oder anderen Bilds](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Vorgehensweise: Bearbeiten eines Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Vorgehensweise: Verwenden eines Zeichentools](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
