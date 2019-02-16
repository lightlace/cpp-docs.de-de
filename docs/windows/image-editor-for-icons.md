---
title: Bildbearbeitung für Symbole
ms.date: 10/17/2018
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.texttool
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- editors, images
- resource editors [C++], graphics
- Image editor [C++]
- resource editors [C++], Image editor
- Image menu
- Grid Settings dialog box [C++]
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
- toolbars [C++], showing
- toolbars [C++], hiding
- text, adding to an image
- Text Tool dialog box [C++]
- Text Tool Font dialog box [C++]
- fonts, changing on an image
- text, on images
- graphics editor [C++]
- Image editor [C++], panes
- Image editor [C++], magnification
- grids, pixel
- pixel grid, Image editor
- Image editor [C++], pixel grid
- Image editor [C++], grid settings
- grid settings, Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
ms.openlocfilehash: 48b363b7b9021042fe6242be70c74f0daeade0c2
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320704"
---
# <a name="image-editor-for-icons"></a>Bildbearbeitung für Symbole

Wenn Sie auf eine Bilddatei (z. B. ico, BMP, PNG) im Projektmappen-Explorer klicken, öffnet das Bild im Bild-Editor auf die gleiche Weise, die Codedateien im Code-Editor geöffnet. Wenn eine Registerkarte Bild-Editor aktiv ist, sehen Sie Symbolleisten mit vielen Tools zum Erstellen und Bearbeiten von Bildern. Zusammen mit Bitmaps, Symbolen und Cursorn können Sie Bilder im GIF- oder JPEG-Format mit Befehlen im Bearbeiten der **Image** Menü und die Tools auf die **Bildbearbeitung** Symbolleiste.

Grafische Ressourcen sind die Images, die Sie für Ihre Anwendung zu definieren. Sie können freehand zeichnen oder Formen zu zeichnen. Sie können auswählen, Bestandteilen eines Bilds für die Bearbeitung, kippen oder Ändern der Größe oder können Sie benutzerdefinierten Pinsel aus einem ausgewählten Teil eines Images erstellen und zeichnen Sie mit dieser Pinsel. Sie können Eigenschaften zu definieren, speichern Sie Bilder in verschiedenen Formaten und Konvertieren von Bildern von einem Format in eine andere.

Zusätzlich zum Erstellen neuer grafische Ressourcen, können Sie [Importieren vorhandener Bilder](../windows/how-to-import-and-export-resources.md) zum Bearbeiten und diese dann zu Ihrem Projekt hinzufügen. Sie können auch öffnen, und Bearbeiten von Bildern, die nicht Teil eines Projekts für sind [unabhängig bearbeiten](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md).

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

Von der Bildbearbeitung werden die folgenden Aufgaben unterstützt:

- [Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)

- [Arbeiten Sie mit Symbolen und Cursorn: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [Verwenden von Zugriffstasten für den Grafik-Editor](../windows/accelerator-keys-image-editor-for-icons.md)

Die **Bildbearbeitung** Fenster zeigt zwei Ansichten eines Bilds mit einem Fensterteiler die zwei Bereiche. Zum Ändern der relativen Größe der Fensterbereiche kann der Fensterteiler seitlich gezogen werden. Der aktive Bereich ist von einem Markierungsrahmen umgeben.

Die **Bildbearbeitung** Fenster entsprechend Ihren Anforderungen und Prioritäten angepasst werden kann. Sie können den [Vergrößerungsfaktor ändern](../windows/changing-the-magnification-factor-image-editor-for-icons.md) und das [Pixelraster ein- oder ausblenden](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

## <a name="image-menu"></a>Menü "Bild"

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

## <a name="toolbar"></a>Symbolleiste

Die **Bildbearbeitung** Symbolleiste enthält Tools für die Zeichnung zeichnen, Text eingeben, löschen und Bearbeiten von Ansichten. Sie enthält außerdem eine Optionsauswahl, mit der Sie Optionen für die Verwendung jedes Tools auswählen können. Sie können z. B. aus verschiedenen Pinsel breiten Vergrößerungsfaktoren und linienformaten.

> [!NOTE]
> Alle Tools zur Verfügung, auf die **Bild-Editor** Symbolleiste stehen auch über die **Image** Menü (unter der **Tools** Befehl).

![Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbar.gif "VcImageEditorToolbar") Symbolleiste der Bildbearbeitung

Verwenden der **Bildbearbeitung** Symbolleiste und **Option** Auswahl, wählen Sie das Tool oder option werden sollen.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

Mit der **Option** Auswahl können Sie die Breite einer Zeile, Pinselstrich usw. angeben. Das Symbol auf der **Option** Selektor Schaltfläche ändert sich je nachdem welches Tool Sie ausgewählt haben.

![Zeichnen von&#45;Shape-Selektor auf der Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbaroptionselector.gif "VcImageEditorToolbarOptionSelector") Optionsauswahl auf der Symbolleiste der Bildbearbeitung

### <a name="use-the-text-tool-dialog-box"></a>Verwenden Sie das Dialogfeld "Texttool"

Verwenden der **Texttool** Dialogfeld zum Hinzufügen von Text mit einem Cursor, Bitmap oder Symbol.

Um dieses Dialogfeld zuzugreifen, öffnen die [Bildbearbeitung](../windows/window-panes-image-editor-for-icons.md). Wählen Sie **Tools** aus der **Image** Menü, und wählen Sie dann die **Texttool** Befehl.

#### <a name="font-button"></a>Schaltfläche "Schriftart"

Öffnet die **Schriftart für Texttool** Dialogfeld, in dem Sie die Schriftart, Schriftschnitt oder Schriftgrad Cursor ändern können. Änderungen werden angewendet, um den Text in die **Text** Bereich.

Um dieses Dialogfeld zuzugreifen, wählen die **Schriftart** Schaltfläche der **Texttool** Dialogfeld. Die Eigenschaften, die verfügbar sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Schriftart**|Listet die verfügbaren Schriftarten an.|
|**Schriftschnitt**|Listet die verfügbaren Formate für die angegebene Schriftart an.|
|**Size**|Listet die verfügbaren Punktgrößen für die angegebene Schriftart an.|
|**Beispiel**|Zeigt ein Beispiel, wie Text mit den Einstellungen für die angegebene Schriftart angezeigt wird.|
|**Skript**|Listet die verfügbaren Sprachskripts für die angegebene Schriftart. Wenn Sie ein Skript für die andere Sprache auswählen, wird der Zeichensatz für, dass die Sprache für die Erstellung von multilingual Dokumente verfügbar.|

So ändern Sie die Schriftart des Texts in einem Bild:

Das folgende Verfahren ist ein Beispiel zum Hinzufügen von Text auf ein Symbol in einer Windows-Anwendung, und bearbeiten die Schriftart des Textes.

1. Erstellen einer C++-Windows Forms-Anwendung. Weitere Informationen finden Sie unter [Erstellen eines Windows-Anwendungsprojekts](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5). Ein *app.ico* Datei wird standardmäßig zum Projekt hinzugefügt.

1. In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei *app.ico*. Die [Bildbearbeitung](../windows/image-editor-for-icons.md) wird geöffnet.

1. Von der **Image** , wählen Sie im Menü **Tools** und wählen Sie dann **Texttool**. Die **Texttool** Dialogfeld wird angezeigt.

1. In der **Texttool** (Dialogfeld), Typ *C++* in den leeren Textbereich. Dieser Text wird angezeigt, in einem in der Größe veränderbaren befindet sich in der oberen linken Ecke des *app.ico*in die **Bildbearbeitung**.

1. In der **Bildbearbeitung**, ziehen Sie das Kontrollkästchen in der Größe veränderbaren in der Mitte des app.ico, um die Lesbarkeit von Text zu verbessern.

1. In der **Texttool** wählen Sie im Dialogfeld die **Schriftart** Schaltfläche. Die **Schriftart für Texttool** Dialogfeld wird angezeigt.

1. In der **Schriftart für Texttool** wählen Sie im Dialogfeld **Times New Roman** aus der Liste der verfügbaren Schriftarten, die in aufgeführt sind die **Schriftart** Listenfeld.

1. Wählen Sie **fett** aus der Liste der verfügbaren Schriftschnitte aufgeführt, die der **Schriftschnitt** Listenfeld.

1. Wählen Sie **10** zeigen Sie auf der Liste der verfügbaren Größen der **Größe** Listenfeld.

1. Klicken Sie auf die Schaltfläche **OK**. Die **Schriftart für Texttool** wird das Dialogfeld zu schließen und die schriftarteinstellungen der neuen in den Text gelten.

1. Wählen Sie die **schließen** Schaltfläche der **Texttool** im Dialogfeld. Das Feld mit veränderbarer Größe, um den Text nicht mehr auf die **Bildbearbeitung**.

#### <a name="text-area"></a>Textbereich

Zeigt den Text, der als Teil der Ressource angezeigt wird. Dieser Bereich ist zunächst leer.

> [!NOTE]
> Wenn **transparenten Hintergrund** festgelegt ist, wird nur der Text in das Image platziert werden. Wenn **nicht transparenter Hintergrund** festgelegt ist, wird ein umschließendes Rechteck, gefüllt mit dem [Hintergrundfarbe](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), hinter dem Text platziert werden. Weitere Informationen finden Sie unter [Auswählen eines transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Sie können mit der rechten Maustaste auf die **Texttool** im Dialogfeld ein standardmäßigen Kontextmenü zugreifen, die eine Liste der standard-Windows-Befehle enthält.

### <a name="to-display-or-hide-the-image-editor-toolbar"></a>Zum Anzeigen oder Ausblenden der Symbolleiste der Bildbearbeitung

Da viele der Zeichenwerkzeuge aus verfügbar sind die [Tastatur](../windows/accelerator-keys-image-editor-for-icons.md), manchmal ist es sinnvoll, zum Ausblenden der **Bildbearbeitung** Symbolleiste.

Auf der **Ansicht** , wählen Sie im Menü **Symbolleisten** wählen Sie dann **Bildbearbeitung**.

   > [!NOTE]
   > Diese Symbolleiste Elemente aus dem aktuellen Projekt nicht verfügbar, wenn eine Image-Datei angezeigt werden, oder Lösung ist nicht geöffnet, in der **Bildbearbeitung**. Finden Sie unter [erstellen ein Symbol oder andere Bild](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), Weitere Informationen zum Hinzufügen von Bilddateien zu Ihren Projekten.

## <a name="window-panes"></a>Fensterbereiche

Die **Bildbearbeitung** Fenster zeigt ein Bild in der Regel in zwei Bereiche, die durch eine Teilerleiste getrennt. Eine Ansicht ist die tatsächliche Größe und der andere wird vergrößert (der Standard-Vergrößerungsfaktor ist 6). Die Ansichten auf diese beiden Bereiche werden automatisch aktualisiert: Änderungen in einem Bereich sofort in die andere angezeigt werden. Die beiden Bereiche erleichtern Sie auf eine vergrößerte Ansicht des Images, arbeiten in der können Sie einzelne Pixel unterscheiden und beobachten zur gleichen Zeit, die Auswirkungen Ihrer Arbeit auf die tatsächliche Größe anzeigen des Bilds.

Im linken Bereich wird so viel Speicherplatz wie erforderlich ist (bis zur Hälfte der der **Image** Fenster) um 1:1 Vergrößerung (Standard) Ihres Images anzuzeigen. Der rechte Bereich zeigt der vergrößerte Abbildung (6:1 Vergrößerung standardmäßig). Sie können ändern, dass die Vergrößerung in jedem Bereich mit der **Magnify** tool die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) oder mithilfe der Zugriffstasten.

Sie können die kleineren Bereich vergrößern der **Bildbearbeitung** Fenster und verwenden Sie die beiden Bereiche, um verschiedene Bereiche des ein großes Bild anzuzeigen. Wählen Sie in den Bereich, um es auszuwählen.

Sie können die relativen Größen der Bereiche ändern, indem Sie den Mauszeiger auf dem Fensterteiler angezeigt, und verschieben Leiste für geteilte nach rechts oder links. Leiste für geteilte kann ganz auf beiden Seiten verschieben, wenn Sie nur einen Bereich arbeiten möchten.

Wenn die **Bildbearbeitung** Bereich vergrößert, um den Faktor 4 oder höher ist, können Sie ein Pixelraster, die die einzelnen Pixel in der Abbildung begrenzt anzeigen.

### <a name="to-change-the-magnification-factor"></a>Ändern des Vergrößerungsfaktors

In der Standardeinstellung die **Image** -Editor zeigt die Ansicht im linken Bereich mit der tatsächlichen Größe und die Ansicht im rechten Bereich auf 6 Mal tatsächliche Größe. Die Vergrößerungsfaktor (in der Statusleiste am unteren Rand des Arbeitsbereichs) ist das Verhältnis zwischen der tatsächlichen Größe des Bilds und die angezeigte Größe. Der Standardfaktor 6 und der Bereich liegt zwischen 1 und 10.

1. Wählen Sie die **Bildbearbeitung** Bereich, dessen Vergrößerungsfaktor ändern möchten.

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), wählen Sie den Pfeil rechts neben der [Tool vergrößern](../windows/toolbar-image-editor-for-icons.md) , und wählen Sie im Untermenü des Vergrößerungsfaktors: **1 X**, **2 X**, **6 X**, oder **8 X**.

   > [!NOTE]
   > Auf einen Vergrößerungsfaktor nicht aufgelistet, die der **Magnify** tool können Sie die Zugriffstasten.

### <a name="to-display-or-hide-the-pixel-grid"></a>Zum Anzeigen oder Ausblenden des Pixelrasters

Für alle **Bildbearbeitung** Bereiche mit einem Vergrößerungsfaktor von 4 oder höher können Sie ein Raster, das die einzelnen Pixel in der Abbildung begrenzt anzeigen.

1. Auf der **Image** , wählen Sie im Menü **Rastereinstellungen**.

1. Wählen Sie die **Pixelraster** Kontrollkästchen, um das Raster anzeigen oder deaktivieren Sie das Kontrollkästchen, um das Raster auszublenden.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

## <a name="visual-studio-image-library"></a>Visual Studio-Bildbibliothek

Sie können kostenlos herunterladen der **Visual Studio-Bildbibliothek** , enthält zahlreiche Animationen, Bitmaps und Symbole, die Sie in Ihren Anwendungen verwenden können. Weitere Informationen über das Herunterladen der Bibliothek finden Sie unter [Die Visual Studio-Bildbibliothek](/visualstudio/designers/the-visual-studio-image-library).

## <a name="managed-resources"></a>Verwaltete Ressourcen

Können Sie die **Image** Editor und die [binär-Editor](binary-editor.md) , Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Die Visual Studio-Ressourcen-Editoren unterstützt nicht das Bearbeiten eingebetteter Ressourcen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Symbole](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)