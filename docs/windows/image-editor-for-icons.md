---
title: Bildbearbeitung für Symbole (C++)
ms.date: 02/15/2019
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
ms.openlocfilehash: dd7da76d3df68fa63c87f64610524accfd4302ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351620"
---
# <a name="image-editor-for-icons-c"></a>Bildbearbeitung für Symbole (C++)

Bei der Auswahl einer Bilddatei (z. B. ico, BMP, PNG) in **Projektmappen-Explorer**, das Bild wird geöffnet, der **Bildbearbeitung** auf die gleiche Weise, die im Code-Dateien öffnen die **Code-Editor** . Wenn ein **Bildbearbeitung** Registerkarte aktiv ist, werden Sie Symbolleisten mit vielen Tools zum Erstellen und Bearbeiten von Bildern finden Sie unter. Zusammen mit Bitmaps, Symbolen und Cursorn können Sie Bilder im GIF- oder JPEG-Format mit Befehlen im Bearbeiten der **Image** Menü und die Tools auf die **Bildbearbeitung** Symbolleiste.

Grafische Ressourcen sind die Images, die Sie für Ihre Anwendung zu definieren. Sie können freehand zeichnen oder Formen zu zeichnen. Sie können auswählen, Bestandteilen eines Bilds für die Bearbeitung, kippen oder Ändern der Größe oder können Sie benutzerdefinierten Pinsel aus einem ausgewählten Teil eines Images erstellen und zeichnen Sie mit dieser Pinsel. Sie können Eigenschaften zu definieren, speichern Sie Bilder in verschiedenen Formaten und Konvertieren von Bildern von einem Format in eine andere.

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

Können Sie auch die **Bildbearbeitung** und [Binär-Editor](binary-editor.md) , Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Die Visual Studio-Ressourcen-Editoren unterstützt nicht das Bearbeiten eingebetteter Ressourcen.

Zusätzlich zum Erstellen neuer grafische Ressourcen, können Sie [Importieren vorhandener Bilder](../windows/how-to-copy-resources.md#import-and-export-resources) zum Bearbeiten und diese dann zu Ihrem Projekt hinzufügen. Sie können auch öffnen, und Bearbeiten von Bildern, die nicht Teil eines Projekts für sind [unabhängig bearbeiten](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md).

Informationen zu den **Bild-Editor**, finden Sie unter Vorgehensweise [erstellen Sie ein Symbol oder andere Bild](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), [Bearbeiten eines Bildes](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), [Verwenden eines Zeichentools](../windows/using-a-drawing-tool-image-editor-for-icons.md), [Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md), und [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md).

> [!NOTE]
> Laden Sie kostenlos die **Visual Studio-Bildbibliothek** , enthält zahlreiche Animationen, Bitmaps und Symbole, die Sie in Ihren Anwendungen verwenden können. Weitere Informationen zur Vorgehensweise beim Herunterladen der Bibliotheks finden Sie unter den [Visual Studio-Bildbibliothek](/visualstudio/designers/the-visual-studio-image-library).

## <a name="image-menu"></a>Menü "Bild"

Die **Image** Menü wird, nur, wenn angezeigt die **Bild-Editor** aktiv ist, enthält Befehle zum Bearbeiten von Bildern, Verwalten von Farbpaletten und festlegen **Bildbearbeitung** Fenster Optionen. Darüber hinaus sind die Befehle für die Verwendung von Gerätebildern verfügbar, beim Arbeiten mit Symbolen und Cursorn.

|Befehl|Beschreibung|
|---|---|
|**Farben umkehren**|Kehrt die verwendeten Farben an.|
|**Horizontal spiegeln**|Kippt das Bild oder die Markierung horizontal.|
|**Vertikal spiegeln**|Kippt das Bild oder die Auswahl vertikal.|
|**90 Grad drehen**|Dreht das Bild oder die Auswahl um 90 Grad.|
|**Anzeigen des Fensters "Farben"**|Öffnet die **Farben** Fenster, in dem Sie die Farben, die für Ihr Image verwenden können.|
|**Auswahl als Pinsel verwenden**|Ermöglicht Ihnen die Erstellung von benutzerdefinierten Pinseln aus einem Teil eines Bilds.<br/><br/>Ihre Auswahl wird es sich um einen benutzerdefinierten Pinsel, der die Farben in der Auswahl auf das Bild verteilt. Kopien der Auswahl bleiben entlang des Pfads ziehen. Sie ziehen, desto langsamer, desto mehr Kopien erfolgen.|
|**Auswahl kopieren und Gliedern**|Erstellt eine Kopie der aktuellen Auswahl und versieht sie mit einer Umrisslinie.<br/><br/>Wenn die Hintergrundfarbe in der aktuellen Auswahl enthalten ist, es wird ausgeschlossen werden, wenn Sie transparenten verfügen ausgewählte.
|**Anpassen von Farben**|Öffnet die **benutzerdefinierte Farbauswahl**, können Sie die Farben anpassen, Sie für Ihr Image verwenden.|
|**Palette laden**|Öffnet die **Palettenfarben laden** Dialogfeld, das Ihnen ermöglicht, das Laden von Palettenfarben, die zuvor in einer PAL-Datei gespeichert.|
|**Palette speichern**|Die Palettenfarben speichert einer PAL-Datei.|
|**Deckend zeichnen**|Bei Auswahl dieser Option wird die aktuelle Auswahl nicht transparent.<br/><br/>Wenn diese Option deaktiviert ist, wird die aktuelle Auswahl transparent.|
|**Symbolleisten-Editor**|Öffnet die [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md).|
|**Rastereinstellungen**|Öffnet die **Rastereinstellungen** Dialogfeld, in dem Sie Raster für das Image angeben können.|
|**Neuer Bildtyp**|Öffnet die [neu \<Gerät > Bildtyp (Dialogfeld)](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md).<br/><br/>Eine einzelnes Symbol-Ressource kann mehrere Images mit verschiedenen Größen enthalten, und Windows können der Größe der entsprechenden Symbole je nachdem, wie sich das alles angezeigt werden soll. Ein neuer Gerätetyp nicht ändert die Größe des Symbols, aber stattdessen erstellt ein neues Image innerhalb des Symbols. Gilt nur für Symbole und Cursor.|
|**Aktuelle Symbol/Cursorbildtyp**|Öffnet ein Untermenü, in der die ersten neun verfügbaren Cursor oder ein Symbol-Images aufgeführt. Klicken Sie im Untermenü mit dem letzten Befehl **weitere**, öffnet der [öffnen \<Gerät > Bild (Dialogfeld)](../windows/open-device-image-dialog-box-image-editor-for-icons.md).|
|**Bildtyp löschen**|Löscht das Image des ausgewählten Geräts an.|
|**Extras**|Öffnet ein Untermenü, das alle verfügbaren aus Tools enthält die **Bildbearbeitung** Symbolleiste.|

Die **Rastereinstellungen** Dialogfeld können Sie die Einstellungen für das Image angeben und Gitternetzlinien angezeigt, auf das Bild bearbeitet. Die Zeilen sind nützlich für das Abbild zu bearbeiten, aber nicht als Teil des Bilds selbst gespeichert.

|Eigenschaft|Beschreibung|
|---|---|
|**Pixelraster**|Wenn diese Option aktiviert ist, zeigt ein Raster an, um jedes Pixel in der **Bildbearbeitung**.<br/><br/>Das Raster, die nur auf 4 × und höherer Auflösung angezeigt wird.|
|**Linienraster**|Bei Auswahl dieser Option zeigt ein Raster an, um Blöcke von Pixeln in der **Bildbearbeitung**, durch die Werte der Raster-Abstand angegeben.|
|**Width**|Gibt die Breite jedes Blocks Kachel.<br/><br/>Diese Eigenschaft ist nützlich, beim Zeichnen von Bitmaps, enthält mehrere Images, die in regelmäßigen Abständen angeordnet sind.|
|**Height**|Gibt die Höhe jedes Blocks Kachel.<br/><br/>Diese Eigenschaft ist nützlich, beim Zeichnen von Bitmaps, enthält mehrere Images, die in regelmäßigen Abständen angeordnet sind.|

## <a name="toolbar"></a>Symbolleiste

Die **Bildbearbeitung** Symbolleiste enthält Tools für die Zeichnung zeichnen, Text eingeben, löschen und Bearbeiten von Ansichten. Sie enthält außerdem eine Optionsauswahl, mit der Sie Optionen für die Verwendung jedes Tools auswählen können. Sie können z. B. aus verschiedenen Pinsel breiten Vergrößerungsfaktoren und linienformaten.

Alle Tools zur Verfügung, auf die **Bildbearbeitung** Symbolleiste sind auch über das Menü **Image** > **Tools**. Verwenden der **Bildbearbeitung** Symbolleiste und **Option** Auswahl, wählen Sie das Tool oder option werden sollen.

![Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbar.gif "VcImageEditorToolbar")<br/>
**Bild-Editor** Symbolleiste

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

Da viele der Zeichenwerkzeuge aus verfügbar sind die [Tastatur](../windows/accelerator-keys-image-editor-for-icons.md), manchmal ist es sinnvoll, zum Ausblenden der **Bildbearbeitung** Symbolleiste.

- Anzeigen oder Ausblenden der **Bild-Editor** Symbolleiste wechseln Sie zum Menü **Ansicht** > **Symbolleisten** , und wählen Sie **Bildbearbeitung**.

> [!NOTE]
> Elemente dieser Symbolleiste werden nicht verfügbar, wenn eine Image-Datei angezeigt, aus dem aktuellen Projekt oder Projektmappe nicht geöffnet, in der **Bildbearbeitung**.

### <a name="option-selector"></a>Optionsauswahl

Mit der **Option** Auswahl können Sie die Breite einer Zeile, Pinselstrich usw. angeben. Das Symbol auf der **Option** Selektor Schaltfläche ändert sich je nachdem welches Tool Sie ausgewählt haben.

![Zeichnen von&#45;Shape-Selektor auf der Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbaroptionselector.gif "VcImageEditorToolbarOptionSelector")<br/>
**Option** -Selektor auf die **Bildbearbeitung** Symbolleiste

### <a name="text-tool"></a>Text-tool

Verwenden der **Texttool** Dialogfeld zum Hinzufügen von Text mit einem Cursor, Bitmap oder Symbol.

Um dieses Dialogfeld zuzugreifen, öffnen die **Bildbearbeitung** und wechseln Sie zum Menü **Image** > **Tools**, und wählen Sie dann die **Text-Tool** -Befehl.

> [!TIP]
> Sie können mit der rechten Maustaste auf die **Texttool** im Dialogfeld ein standardmäßigen Kontextmenü zugreifen, die eine Liste der standard-Windows-Befehle enthält.

Öffnen der **Schriftart für Texttool** Dialogfeld zum Ändern der Schriftart, Schriftschnitt oder Schriftgrad Cursor. Änderungen werden angewendet, um den Text in die **Text** Bereich.

Um dieses Dialogfeld zuzugreifen, wählen die **Schriftart** Schaltfläche der **Texttool** Dialogfeld. Die Eigenschaften, die verfügbar sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Schriftart**|Listet die verfügbaren Schriftarten an.|
|**Schriftschnitt**|Listet die verfügbaren Formate für die angegebene Schriftart an.|
|**Size**|Listet die verfügbaren Punktgrößen für die angegebene Schriftart an.|
|**Beispiel**|Zeigt ein Beispiel, wie Text mit den Einstellungen für die angegebene Schriftart angezeigt wird.|
|**Skript**|Listet die verfügbaren Sprachskripts für die angegebene Schriftart.<br/><br/>Wenn Sie ein Skript für die andere Sprache auswählen, wird der Zeichensatz für, dass die Sprache für die Erstellung von multilingual Dokumente verfügbar.|

#### <a name="to-change-the-font-of-text-on-an-image"></a>Ändern die Schriftart von Text in einem Bild

Hier ist ein Beispiel zum Hinzufügen von Text auf ein Symbol in einer Windows-Anwendung, und bearbeiten die Schriftart des Textes.

1. Erstellen einer C++-Windows Forms-Anwendung. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Windows Forms-Anwendungen](/previous-versions/visualstudio/visual-studio-2008/s69bf10x(v%3dvs.90)). Ein *app.ico* Datei wird standardmäßig zum Projekt hinzugefügt.

1. In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei *app.ico*. Die **Bildbearbeitung** wird geöffnet.

1. Wechseln Sie zum Menü **Image** > **Tools** , und wählen Sie **Texttool**.

1. In der **Texttool** (Dialogfeld), Typ *C++* in den leeren Textbereich. Dieser Text wird angezeigt, in einem in der Größe veränderbaren befindet sich in der oberen linken Ecke des *app.ico* in die **Bildbearbeitung**.

1. In der **Bildbearbeitung**, ziehen Sie das Feld mit anpassbarer Größe in der Mitte des *app.ico* verbessern die Lesbarkeit von Text.

1. In der **Texttool** wählen Sie im Dialogfeld die **Schriftart** Schaltfläche.

1. In der **Schriftart für Texttool** Dialogfeld:

   - Wählen Sie **Times New Roman** aus der Liste der verfügbaren Schriftarten, die in aufgeführt sind die **Schriftart** Listenfeld.

   - Wählen Sie **fett** aus der Liste der verfügbaren Schriftschnitte aufgeführt, die der **Schriftschnitt** Listenfeld.

   - Wählen Sie **10** zeigen Sie auf der Liste der verfügbaren Größen der **Größe** Listenfeld.

   - Klicken Sie auf **OK**. Die **Schriftart für Texttool** wird das Dialogfeld zu schließen und die schriftarteinstellungen der neuen in den Text gelten.

1. Wählen Sie **schließen** auf die **Texttool** Dialogfeld. Das Feld mit veränderbarer Größe, um den Text nicht mehr auf die **Bildbearbeitung**.

Der Textbereich zeigt den Text, der als Teil der Ressource angezeigt wird. Dieser Bereich ist zunächst leer.

> [!NOTE]
> Wenn **transparenten Hintergrund** festgelegt ist, wird nur der Text in das Image platziert werden. Wenn **nicht transparenter Hintergrund** festgelegt ist, wird ein umschließendes Rechteck, gefüllt, die mit der Farbe des Hintergrunds hinter dem Text platziert werden.

## <a name="window-panes"></a>Fensterbereiche

Die **Bildbearbeitung** Fenster zeigt zwei Ansichten eines Bilds mit einem Fensterteiler die zwei Bereiche. Zum Ändern der relativen Größe der Fensterbereiche kann der Fensterteiler seitlich gezogen werden. Der aktive Bereich ist von einem Markierungsrahmen umgeben.

Eine Ansicht ist die tatsächliche Größe, und der andere wird mit dem Standardwert Vergrößerung Faktor 6 vergrößert. Die Ansichten auf diese beiden Bereiche werden automatisch aktualisiert, die in einem Bereich vorgenommenen Änderungen werden sofort angezeigt, in der anderen. Die beiden Bereiche erleichtern Sie auf eine vergrößerte Ansicht des Images, arbeiten in der können Sie einzelne Pixel unterscheiden und beobachten zur gleichen Zeit, die Auswirkungen Ihrer Arbeit auf die tatsächliche Größe anzeigen des Bilds.

Im linken Bereich wird so viel Speicherplatz wie erforderlich ist (bis zur Hälfte der der **Image** Fenster) die Standardansicht für die 1:1 Vergrößerung des Bilds angezeigt. Im rechte Bereich zeigt eine vergrößerte 6:1 Vergrößerung Standardbild. Sie können ändern, dass die Vergrößerung in jedem Bereich mit der **Magnify** tool die **Bildbearbeitung** Symbolleiste oder mithilfe der Zugriffstasten.

Sie können die kleineren Bereich vergrößern der **Bildbearbeitung** Fenster und verwenden Sie die beiden Bereiche, um verschiedene Bereiche des ein großes Bild anzuzeigen. Wählen Sie in den Bereich, um es auszuwählen.

Sie können die relativen Größen der Bereiche ändern, indem Sie den Mauszeiger auf dem Fensterteiler angezeigt, und verschieben Leiste für geteilte nach rechts oder links. Leiste für geteilte kann ganz auf beiden Seiten verschieben, wenn Sie nur einen Bereich arbeiten möchten.

Wenn die **Bildbearbeitung** Bereich vergrößert, um den Faktor 4 oder höher ist, können Sie ein Pixelraster, die die einzelnen Pixel in der Abbildung begrenzt anzeigen.

### <a name="to-change-the-magnification-factor"></a>Ändern des Vergrößerungsfaktors

In der Standardeinstellung die **Bildbearbeitung** zeigt die Ansicht im linken Bereich auf die tatsächliche Größe und die Ansicht im rechten Bereich mit der tatsächlichen Größe 6-Mal. Die Vergrößerungsfaktor (in der Statusleiste am unteren Rand des Arbeitsbereichs) ist das Verhältnis zwischen der tatsächlichen Größe des Bilds und die angezeigte Größe. Der Standardfaktor 6 und der Bereich liegt zwischen 1 und 10.

1. Wählen Sie die **Bildbearbeitung** Bereich, dessen Vergrößerungsfaktor ändern möchten.

1. Auf der **Bildbearbeitung** Symbolleiste wählen Sie den Pfeil rechts neben der **Magnify** Konfigurationstool, und wählen Sie aus dem Untermenü des Vergrößerungsfaktors: **1 X**, **2 X**, **6 X**, oder **8 X**.

   > [!NOTE]
   > Auf einen Vergrößerungsfaktor nicht aufgelistet, die der **Magnify** tool können Sie die Zugriffstasten.

### <a name="to-display-or-hide-the-pixel-grid"></a>Zum Anzeigen oder Ausblenden des Pixelrasters

Für alle **Bildbearbeitung** Bereiche mit einem Vergrößerungsfaktor von 4 oder höher können Sie ein Raster, das die einzelnen Pixel in der Abbildung begrenzt anzeigen.

1. Wechseln Sie zum Menü **Image** > **Rastereinstellungen**.

1. Wählen Sie die **Pixelraster** Kontrollkästchen, um das Raster anzeigen oder deaktivieren Sie das Kontrollkästchen, um das Raster auszublenden.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>

<!--[Icons](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)-->