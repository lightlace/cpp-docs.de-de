---
title: Arbeiten mit Farben (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
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
ms.openlocfilehash: f2ac2cf7eaab0372b9cf349e1544fc5b3426dee6
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850366"
---
# <a name="working-with-color-image-editor-for-icons"></a>Arbeiten mit Farben (Bildbearbeitung für Symbole)

Die **Bildbearbeitung** enthält viele Features, die speziell behandelt und Anpassen von Farben. Sie können eine Vorder- oder Hintergrund Farbe festlegen, füllen von begrenzten Bereichen mit Farbe oder eine andere Farbe auf ein Bild, als die aktuelle Vorder- oder Hintergrund Farbe auswählen. Sie können die Tools verwenden, auf die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) zusammen mit den Farben (Palette) in der **Farben** um Images zu erstellen.

Alle Farben für Monochrom und 16 Farben-Images werden angezeigt, der **Farben** Palette in der **Farben** Fenster. Zusammen mit 16 Standardfarben können Sie eigene benutzerdefinierten Farben erstellen. Ändern der Farben in der Palette ändert sich sofort auf die entsprechende Farbe im Bild aus.

Beim Arbeiten mit 256-Farben-Symbol und der Cursor-Images, die **Farben** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) verwendet wird. Weitere Informationen finden Sie unter [Erstellen eines 256-Farben-Symbols oder Cursors](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

True Color-Bilder können auch erstellt werden. Jedoch nicht "true" Farbmuster angezeigt, in der vollständigen Palette in der **Farben** Fenster; sie werden nur in den Vorder- oder Hintergrund Indikator Farbbereich. "True" Farben werden erstellt, mit der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).

Sie können benutzerdefinierte Farbpaletten auf Datenträger speichern und erneut geladen werden, je nach Bedarf. Die zuletzt verwendeten Farben-Palette ist in der Registrierung gespeichert und beim nächsten start von Visual Studio automatisch geladen.

## <a name="select-foreground-or-background-colors"></a>Auswählen von Vordergrund-oder Hintergrundfarben

Mit Ausnahme der **Radierer**, tools auf die **Bildbearbeitung** Symbolleiste Zeichnen-Befehl in der aktuellen Vordergrund- oder Hintergrundfarbe, wenn Sie die linke oder rechte Maustaste drücken.

### <a name="to-select-a-foreground-color"></a>So wählen Sie eine Vordergrundfarbe aus

Die linke Maustaste gedrückt, wählen Sie die gewünschte Farbe auf den **Farben** Palette.

### <a name="to-select-a-background-color"></a>So wählen Sie eine Hintergrundfarbe aus

Mit der rechten Maustaste, wählen Sie die gewünschte Farbe auf den **Farben** Palette.

## <a name="filling-a-bounded-area-of-an-image-with-a-color"></a>Füllen von begrenzten Bereichen eines Bildes mit einer Farbe

Die bildbearbeitung bietet die **füllen** Tool für das Füllen alle Bildbereiche mit der aktuellen zeichnen oder die aktuelle Hintergrundfarbe.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

### <a name="to-use-the-fill-tool"></a>Um das Füllwerkzeug verwenden

1. Auf der **Bild-Editor** Symbolleiste (oder die **Image** Menü **Tools** Befehl), wählen die **füllen** Tool.

1. Wählen Sie ggf. die Farben Zeichnen: In der [Farben (Palette)](../windows/colors-window-image-editor-for-icons.md), wählen Sie die linke Maustaste gedrückt, wählen Sie eine Vordergrundfarbe oder der rechten Maustaste auf eine Hintergrundfarbe auswählen.

1. Verschieben der **Füllung** Tool, um den Bereich, die Sie füllen möchten.

1. Wählen Sie die linke oder rechte Maustaste-Schaltfläche bzw. mit der Vordergrund- oder die Hintergrundfarbe zu füllen.

## <a name="pick-up-a-color-from-an-image-to-use-elsewhere"></a>Nehmen Sie eine Farbe aus einem Image, um die an anderer Stelle verwenden.

Die **Farbe auswählen**, oder verwandelt, Tool macht eine beliebige Farbe auf das Bild der aktuellen Vordergrund- oder Hintergrundfarbe, je nachdem, ob Sie links oder die rechte Maustaste drücken. Zum Abbrechen der **Farbe auswählen** tool, und wählen Sie ein anderes Tool.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

### <a name="to-pick-up-a-color"></a>Auswählen einer Farbe

1. Auf der **Bild-Editor** Symbolleiste (oder von der **Image** Menü **Tools** Befehl), wählen die **Farbe auswählen** Tool.

1. Wählen Sie die Farbe, die Sie aus dem Image übernehmen möchten.

   > [!NOTE]
   > Nachdem Sie eine Farbe aus, übernehmen die **Image** -Editor-Datencenter erneut funktionsfähig, die zuletzt verwendete Tool.

1. Verwenden die linke Maustaste gedrückt für die Vordergrundfarbe darstellt, oder die rechte Maustaste der Hintergrundfarbe gezeichnet werden soll.

## <a name="choose-a-transparent-or-opaque-background"></a>Auswählen eines transparenten oder deckenden Hintergrunds

Beim Verschieben oder kopieren eine Auswahl aus einem Image, alle Pixel in der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen, sind standardmäßig transparent, und sie nicht am Zielspeicherort Pixel verdecken.

Sie können über einen transparenten Hintergrund (Standard) wechseln, um ein nicht transparenter Hintergrund und wieder zurück. Wenn Sie eine Auswahltool verwenden, die **transparenten Hintergrund** und **nicht transparenter Hintergrund** Optionen angezeigt, der **Option** -Selektor auf die **Bildbearbeitung** Symbolleiste (siehe unten).

![Optionen im Hintergrund &#45; undurchsichtig oder durchsichtig](../windows/media/vcimageeditoropaqtranspback.gif "Optionen im Hintergrund &#45; undurchsichtig oder durchsichtig")<br/>
**Transparente und undurchsichtige Optionen** auf die **Symbolleiste der Bildbearbeitung**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>So wechseln Sie zwischen einem transparente und undurchsichtige-Hintergrund

In der **Bildbearbeitung** -Symbolleiste auf die **Option** Auswahl, und wählen Sie dann den entsprechenden Hintergrund:

   - `Opaque Background (O)`: Vorhandene Bild wird von allen Bereichen der Auswahl verdeckt.

   - `Transparent Background (T)`: Vorhandenes Bild zeigt Teile der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen.

   \- oder –

Auf der **Image** Menü aktivieren oder deaktivieren Sie **Deckend zeichnen**.

Sie können die Farbe des Hintergrunds ändern, während eine Auswahl bereits aktiv ist ändern, welche Teile des Bilds transparent sind.

## <a name="invert-the-colors-in-a-selection"></a>Invertieren der Farben in einer Markierung

Die **Image** Editor bietet eine bequeme Möglichkeit zum Invertieren von Farben im ausgewählten Teil des Bilds, sodass Sie erkennen können, wie ein Bild mit invertierten Farben aussieht.

### <a name="to-invert-colors-in-the-current-selection"></a>So kehren Sie Farben in der aktuellen Auswahl um

Auf der **Image** , wählen Sie im Menü **Farben umkehren**.

## <a name="customize-or-change-colors"></a>Anpassen oder Ändern von Farben

Die **Image** Anmerkung der Redaktion **Farben** Palette werden anfänglich 16 Standardfarben angezeigt. Mit den bereits angezeigten Farben können Sie auch eigene benutzerdefinierten Farben erstellen. Sie können dann [speichern und Laden Sie eine benutzerdefinierte Farbpalette](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md).

Die **benutzerdefinierte Farbauswahl** Dialogfeld können Sie die Farben anpassen, Sie für Ihr Image verwenden. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|--------------------------|--------------------------|
|**Farbverlauf Farbanzeige**|Ändert die Werte einer ausgewählten Farbe. Positionieren Sie das Fadenkreuz, auf die Farbe, die Sie ändern möchten. Klicken Sie dann den Schieberegler nach oben oder unten, um Änderungen der Helligkeit oder RGB-Werte der Farbe.|
|**Helligkeits-Symbolleiste**|Legt die Helligkeit für die Farbe, die Sie, in Auswählen der **Farbverlauf Farbanzeige** Feld. Wählen Sie aus, und ziehen Sie den weißen Pfeil der Balken für größere Helligkeit oder nach unten bei kleiner. Die **Farbe** Feld zeigt die Farbe, die Sie ausgewählt haben und die Auswirkungen der Helligkeit, die Sie festlegen.|
|**Farbe**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Hue**|Listet den Farbton (Farbwert für rad) der Farbe, die Sie definieren. Werte zwischen 0 und 240, in denen 0 ist rot, 60 ist gelb gekennzeichnet, 120 ist Grün, 180 beträgt Cyan, Magenta "200" lautet und 240 ist Blau.|
|**Sätt.:**|Gibt an, der Sättigungswert der Farbe, die Sie definieren. Die Sättigung ist die Menge des in einem angegebenen Farbton. Werte zwischen 0 und 240.|
|**Lum**|Listet die Brillanz (Helligkeit) der Farbe, die Sie definieren. Werte zwischen 0 und 240.|
|**Rot**|Gibt den Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Grün**|Gibt den grünen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|
|**Blau**|Gibt den blauen Wert der Farbe, die Sie definieren. Werte zwischen 0 und 255 liegen.|

### <a name="to-change-colors-on-the-colors-palette"></a>So ändern Sie die Farben in der Farbpalette

1. Von der **Image** Menü wählen **Farben anpassen**.

1. In der **benutzerdefinierte Farbauswahl** Dialogfeld Feld, definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben, oder wählen Sie eine Farbe in der **Farbverlauf Farbanzeige** Feld.

1. Legen Sie die Helligkeit durch Verschieben des Schiebereglers auf der **Helligkeit** Leiste.

1. Viele benutzerdefinierte Farben werden gedithert. Wenn Sie der Volltonfarbe entspricht, die der Ditheringfarbe Farbe am nächsten möchten, doppelklicken Sie auf die **Farbe** Feld.

   Wenn Sie später die geditherte Farbe angezeigt werden sollen, verschieben Sie den Schieberegler auf die **Helligkeit** Balken- oder verschieben Sie das Fadenkreuz, in der **Farbverlauf Farbanzeige** Feld erneut aus, um das dithering wiederherzustellen.

1. Wählen Sie **OK** auf die neue Farbe hinzuzufügen.

## <a name="save-and-load-different-color-palettes"></a>Speichern und Laden von verschiedenen Farbpaletten

Sie können das Speichern und Laden eine **Farben** Palette mit benutzerdefinierten Farben an. (Standardmäßig die **Farben** zuletzt verwendete Farbpalette wird automatisch geladen, wenn Sie Visual Studio starten.)

> [!TIP]
> Da die **Image** -Editor verfügt über keine Möglichkeit zum Wiederherstellen der standardmäßigen **Farben** Palette, speichern Sie die Standardeinstellung **Farben** unter einem Namen wie z. B.  *Standard.PAL* oder *default.pal* , damit Sie die Standardeinstellungen problemlos wiederherstellen können.

Verwenden Sie die **Palettenfarben laden** Dialogfeld spezielle Farbpaletten, die für die Verwendung in Ihrem C++-Projekt zu laden. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|-----------------|-----------------|
|**Suchen in**|Gibt den Speicherort einer Datei oder eines Ordners gefunden werden sollen. Wählen Sie den Pfeil, um einen anderen Speicherort auswählen, oder wählen Sie das Ordnersymbol auf der Symbolleiste können Sie Ebenen zu verschieben.|
|**Dateiname**|Dient zur Eingabe der Name der Datei, die Sie öffnen möchten. Um schnell eine Datei zu suchen, die Sie zuvor erstellt haben, wählen Sie den Dateinamen in der Dropdown-Liste, sofern verfügbar.<br/><br/>Wenn Sie für eine Datei durchsuchen, können Sie Sternchen (*) als Platzhalter verwenden. Sie können z. B. eingeben \*.\* um eine Liste aller Dateien anzuzeigen. Sie können auch den vollständigen Pfad einer Datei, z. B. C:\My Documents\MyColorPalette.pal eingeben oder \\\NetworkServer\MyFolder\MyColorPalette.pal.|
|**Dateityp**|Listet die Typen der anzuzeigenden Dateien. Palette (*. PAL) ist der Standardtyp für die Datei für Farbpaletten.|

### <a name="to-save-a-custom-colors-palette"></a>So speichern Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette speichern**.

1. Navigieren Sie zu dem Verzeichnis, in dem Sie die Farbpalette speichern möchten, und geben Sie einen Namen für die Palette ein.

1. Klicken Sie auf **Speichern**.

### <a name="to-load-a-custom-colors-palette"></a>So laden Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette laden**.

1. In der **Palettenfarben laden** Dialogfeld Feld, navigieren Sie zum richtigen Verzeichnis aus, und wählen Sie die Palette, die Sie laden möchten. **Farbe** Paletten werden mit der Erweiterung. PAL gespeichert.

## <a name="colors-window"></a>Fenster "Farben"

Die **Farben** Fenster besteht aus zwei Teilen:

- Die **Farben (Palette)**, dies ist ein Array der farbbeispiele, die Farben darstellen können. Sie können die Beispiele, Vordergrund- und Hintergrundfarben auszuwählen, wenn Sie die Grafiktools verwenden auswählen.

- Die **Farbanzeige**, zeigt die Vordergrund- und Hintergrundfarben und Selektoren für die Bildschirm- und invertierte Farbe.

   ![Fenster "Farben"](../windows/media/vccolorswindow.gif "VcColorsWindow")<br/>
   Fenster "Farben"

> [!NOTE]
> Die **Bildschirm Farbe** und **invertierte Farbe** Tools sind nur verfügbar für Symbole und Cursor.

Sie können die **Farben** -Fenster mit der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md).

### <a name="to-display-the-colors-window"></a>Um das Fenster "Farben" anzuzeigen.

Mit der rechten Maustaste einen **Bildbearbeitung** Bereich, und wählen Sie **Fenster "Farben" anzeigen** aus dem Kontextmenü.

   \- oder –

Wählen Sie **anzeigen Fenster "Farben"** auf die [des bildmenüs](../windows/image-menu-image-editor-for-icons.md).

### <a name="to-hide-the-colors-window"></a>So blenden Sie das Fenster "Farben" aus

Lösen Sie das Fenster. Diese Aktion ermöglicht das Fenster automatisch ausgeblendet, wenn er nicht verwendet wird.

\- oder –

Wählen Sie die **schließen** Schaltfläche.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Erstellen transparenter oder invertierter Bereiche in Gerätebildern](../windows/creating-transparent-or-inverse-regions-in-device-images.md)<br/>
[Dialogfeld Benutzerdefinierte Farben](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
[Menü "Bild"](../windows/image-menu-image-editor-for-icons.md)<br/>
