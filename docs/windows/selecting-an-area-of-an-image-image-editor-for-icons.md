---
title: 'Vorgehensweise: Bearbeiten eines Bildes'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.editing
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
- Image editor [C++], flipping and rotating images
- images [C++], flipping
- images [C++], rotating
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
- Image editor [C++], editing images
- images [C++], editing
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
ms.openlocfilehash: 849da0d14987a057d39d5f9531e97545b3d4b8cf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033287"
---
# <a name="how-to-edit-an-image"></a>Vorgehensweise: Bearbeiten eines Bildes

Sie können Tools für die Auswahl verwenden, um einen Bereich eines Bildes zu definieren, die Sie Ausschneiden, kopieren, löschen, ändern Sie die Größe, umkehren, oder verschieben möchten. Mit der **Rechteckauswahl** Tool können Sie definieren, und wählen Sie einen rechteckigen Bereich des Bilds. Mit der **Unregelmäßige Auswahl** Tool können Sie einen Freihand über den Bereich, die Sie auswählen, für das Ausschneiden, kopieren oder andere Vorgänge möchten zeichnen.

> [!NOTE]
> Finden Sie unter der **Rechteckauswahl** und **Unregelmäßige Auswahl** Tools in dargestellte [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) oder die QuickInfos jeder Schaltfläche auf der **Bildbearbeitung** Symbolleiste.

Sie können auch einen benutzerdefinierten Pinsel aus einer Auswahl erstellen. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).

## <a name="how-to"></a>Gewusst wie

Um ein Bild zu bearbeiten, finden Sie unter wie:

### <a name="to-select-an-image"></a>Ein Bild auswählen

1. Verwenden der **Bildbearbeitung** Symbolleiste oder wechseln Sie zum Menü **Image** > **Tools** , und wählen Sie das Auswahlwerkzeug werden sollen.

1. Verschieben Sie die Einfügemarke an einer Ecke des Bereichs, Image, das Sie auswählen möchten. Fadenkreuz wird angezeigt, wenn die Einfügemarke auf das Bild ist.

1. Ziehen Sie die Einfügemarke in die entgegengesetzte Ecke des Bereichs, die Sie auswählen möchten. Ein Rechteck zeigt an, welche Pixel ausgewählt werden. Alle Pixel innerhalb des Rechtecks, u. a. die das Rechteck, sind in der Auswahl enthalten.

1. Lassen Sie die Maustaste los. Der Markierungsrahmen umschließt den ausgewählten Bereich.

#### <a name="to-select-an-entire-image"></a>Auswählen ein ganzen Bildes

Wählen Sie das Bild außerhalb der aktuellen Auswahl. Die Markierungsrahmen umgeben ändert den Fokus, und das gesamte Bild wieder umfasst.

### <a name="to-edit-parts-of-an-image"></a>Bearbeiten von Bestandteilen eines Bilds

Können Sie standard Bearbeitungsvorgänge ausführen – Ausschneiden, kopieren, löschen und verschieben, auf eine [Auswahl](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), ob die Auswahl auf das gesamte Bild oder nur eines Teils davon ist. Da die **Bild-Editor** verwendet die **Windows-Zwischenablage**, können Sie Bilder zwischen übertragen die **Bildbearbeitung** und andere Anwendungen für Windows.

Darüber hinaus können Sie die Auswahl, Größe ändern, ob es sich um das gesamte Bild oder nur einen Teil enthält.

#### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>So schneiden Sie die aktuelle Auswahl und verschieben Sie es in die Zwischenablage

Wechseln Sie zum Menü **bearbeiten** > **Ausschneiden**.

#### <a name="to-copy-the-selection"></a>Um die Auswahl kopieren

1. Positionieren Sie den Zeiger in einen Rahmen oder an einer beliebigen Stelle auf, mit Ausnahme der Ziehpunkte.

1. Halten Sie die **STRG** gedrückt, während Sie die Auswahl in eine neue Position ziehen. Der Bereich der ursprünglichen Auswahl ist unverändert.

1. Um die Auswahl in das Abbild an dessen aktuellen Speicherort zu kopieren, wählen Sie außerhalb des Cursors für die Auswahl.

#### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Der Inhalt der Zwischenablage in ein Bild einfügen

1. Wechseln Sie zum Menü **bearbeiten** > **einfügen**.

   Der Inhalt der Zwischenablage, von der Markierungsrahmen umgeben werden in der oberen linken Ecke des Bereichs angezeigt.

1. Positionieren Sie den Zeiger in einen Rahmen, und ziehen Sie das Bild an die gewünschte Position auf dem Bild.

1. Um das Bild an seinem neuen Standort zu verankern, wählen Sie außerhalb der Markierungsrahmen umgeben.

#### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Um die aktuelle Auswahl zu löschen, ohne ihn zu verschieben in die Zwischenablage

Wechseln Sie zum Menü **bearbeiten** > **löschen**.

   Der ursprüngliche Bereich der Auswahl wird mit der aktuellen Hintergrundfarbe gefüllt.

> [!NOTE]
> Sie können den Zugriff auf die **Ausschneiden**, **kopieren**, **einfügen**, und **löschen** Befehle mit der rechten Maustaste die **Ressourcenansicht** Fenster.

#### <a name="to-move-the-selection"></a>Um die Auswahl verschieben

1. Positionieren Sie den Zeiger in einen Rahmen oder an einer beliebigen Stelle auf, mit Ausnahme der Ziehpunkte.

1. Ziehen Sie die Auswahl an die neue Position.

1. Um die Auswahl an die neue Position in das Image zu verankern, wählen Sie außerhalb des Rahmens für die Auswahl.

Weitere Informationen zum Zeichnen mit einer Auswahl, finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).

### <a name="to-flip-an-image"></a>So kippen Sie ein Bild

Sie können ein Bild, um ein spiegelimage der ursprünglichen erstellen, drehen Sie das Bild um, oder das Bild auf der rechten Seite um 90 Grad drehen, zu einem Zeitpunkt drehen oder kippen.

- Das Bild horizontal gekippt (Spiegelbild), wechseln Sie zum Menü **Image** > **Horizontal kippen**.

- Das Bild vertikal gekippt (Kopf), wechseln Sie zum Menü **Image** > **vertikal kippen**.

- Wechseln Sie zum Menü ", um das Bild um 90 Grad drehen, **Image** > **um 90 Grad drehen**.

   > [!NOTE]
   > Können Sie auch die [Zugriffstasten (Tastenkombination)](../windows/accelerator-keys-image-editor-for-icons.md) für diese Befehle oder Zugriff auf die Befehle im Kontextmenü (außerhalb des Abbilds während in select der **Bildbearbeitung**).

### <a name="to-resize-an-image"></a>Um die Größe eines Bilds ändern

Das Verhalten von der **Bildbearbeitung** während größenänderungen bei Bildern abhängig, ob Ihr [ausgewählten](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) das gesamte Bild oder nur eines Teils davon.

Wenn die Auswahl nur einen Teil der Abbildung enthält die **Bildbearbeitung** verringert sich die Auswahl um Löschen von Zeilen oder Spalten von Pixeln, und füllen die frei werdenden Regionen mit der aktuellen Hintergrundfarbe. Sie können auch die Auswahl Strecken, durch das Duplizieren von Zeilen oder Spalten von Pixeln.

Wenn die Auswahl auf das gesamte Bild, enthält die **Bildbearbeitung** entweder verkleinert und das Bild wird gestreckt oder schneidet und erweitert ihn.

Es gibt zwei Mechanismen zum Ändern der Bildgröße: Ziehpunkte und [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie Ziehen der Ziehpunkte, um die Größe des gesamten oder einen Teil eines Bilds zu ändern. Ziehpunkte, die Sie ziehen können, sind gefüllt. Sie können keine Handles ziehen, die leer sind. Verwenden der **Eigenschaften** Fenster zum Ändern der Größe des gesamtes image nur nicht für eine ausgewählte Komponente.

![Ziehpunkte in einer Bitmap](../mfc/media/vcimageeditorsizinghandles.gif "VcImageEditorSizingHandles")<br/>
Ziehpunkte

> [!NOTE]
> Wenn man die **Kachel Raster** gewählten Option in der [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md), klicken Sie dann Ändern der Größe von Snapshots an der nächsten Kachel. Wenn nur die **Pixelraster** Option ist aktiviert (Standardeinstellung), Ändern der Größe von Snapshots und dem nächsten verfügbaren Pixel.

#### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Zum Ändern der Größe eines ganzen Bilds mithilfe des Eigenschaftenfensters

1. Öffnen Sie das Bild, dessen Eigenschaften Sie ändern möchten.

1. In der **Breite** und **Höhe** Dialogfelder in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie die Dimensionen, die Sie möchten.

   Wenn Sie die Größe des Bilds erhöhen, das **Bildbearbeitung** erweitert das Bild an der rechten Seite nach unten, oder beides und füllt Sie die neue Region mit der aktuellen Hintergrundfarbe. Das Bild wird nicht gestreckt.

   Wenn Sie die Größe des Bilds, verkürzen die **Bildbearbeitung** schneidet das Bild auf den rechten oder unteren Rand oder beides.

   > [!NOTE]
   > Können Sie die **Breite** und **Höhe** Eigenschaften, die nur das gesamte Bild nicht zum Ändern der Größe eines markierten Größe zu ändern.

#### <a name="to-crop-or-extend-an-entire-image"></a>Zuschneiden oder Erweitern eines ganzen Bildes

1. Wählen Sie das gesamte Bild.

   Wenn Teil des Images derzeit ausgewählt ist, und Sie das gesamte Bild auswählen möchten, wählen Sie eine beliebige Stelle auf das Bild außerhalb des Rahmens der aktuellen Auswahl.

1. Ziehen Sie einen Ziehpunkt, bis das Bild auf die richtige Größe hat.

In der Regel die **Bildbearbeitung** schneidet oder ein Bild vergrößert, wenn Sie deren Größe ändern, indem Sie einen der Ziehpunkte verschieben. Gedrückter der **UMSCHALT** gedrückt, während Sie einen der Ziehpunkte, Verschieben der **Bildbearbeitung** verkleinert wird oder das Bild gestreckt.

#### <a name="to-shrink-or-stretch-an-entire-image"></a>So verkleinern oder Strecken eines ganzen Bildes

1. Wählen Sie das gesamte Bild.

   Wenn ein Teil des Images derzeit ausgewählt ist, und Sie das gesamte Bild auswählen möchten, wählen Sie eine beliebige Stelle auf das Bild außerhalb des Rahmens der aktuellen Auswahl.

1. Halten Sie die **UMSCHALT** gedrückt, und ziehen Sie einen Ziehpunkt, bis das Bild auf die richtige Größe hat.

#### <a name="to-shrink-or-stretch-part-of-an-image"></a>So verkleinern oder Strecken Teil eines Images

1. Wählen Sie den Teil des Abbilds aus, die Sie anpassen möchten. Weitere Informationen finden Sie unter [Markieren eines Bildbereichs des Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md).

1. Ziehen Sie die Ziehpunkte, bis die Auswahl der richtigen Größe ist.

### <a name="to-edit-an-image-outside-of-a-project"></a>Bearbeiten ein Bilds außerhalb eines Projekts

Sie können öffnen und bearbeiten Images in der Entwicklungsumgebung aus, wie in allen Anwendungen Grafiken, z. B. Öffnen einer Bitmap für die eigenständige Bearbeitung. Die Images, mit denen Sie zusammenarbeiten müssen nicht Teil eines Visual Studio-Projekts sein.

1. Wechseln Sie zum Menü **Datei** > **öffnen**.

1. In der **Dateityp** Kontrollkästchen **alle Dateien**.

1. Suchen Sie und öffnen Sie das Abbild, die, das Sie bearbeiten möchten.

### <a name="to-change-image-properties"></a>Ändern von Bildeigenschaften

Sie können festlegen, oder Ändern der Eigenschaften eines Image mithilfe der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

1. Öffnen Sie das Abbild in der **Bildbearbeitung**.

1. In der **Eigenschaften** Fenster ANY- oder all-Eigenschaften für das Image zu ändern.

   |Eigenschaft|Beschreibung|
   |--------------|-----------------|
   |**Farben**|Gibt an, das Farbschema für das Image. Wählen Sie **Monochrom**, **16**, oder **256**, oder **True Color**.<br/><br/>Wenn Sie bereits das Image mit einem 16-Farben-Palette gezeichnet haben, durch die Auswahl **Monochrom** bewirkt, dass Ersetzungen von Schwarz und weiß, für die Farben in der Abbildung. Kontrast wird nicht immer beibehalten: z. B. benachbarte Bereiche Rot-Grün sind in Schwarz umgewandelt.|
   |**Filename**|Gibt den Namen der Bilddatei.<br/><br/>Standardmäßig weist Visual Studio ein Basisdateiname, entfernen die ersten vier Zeichen ("IDB_") erstellt, aus der Standard-Ressourcen-ID (IDB_BITMAP1) und die entsprechende Erweiterung hinzugefügt. Der Name der Datei für das Bild in diesem Beispiel *BITMAP1.bmp*. Könnten Sie den Namen es *kann in MEINEBITMAP1.bmp*.|
   |**Height**|Legt die Höhe des Bilds (in Pixel) fest. Der Standardwert ist 48.<br/><br/>Das Bild ist beschnitten, oder ein leerer Bereich unterhalb des Bildes hinzugefügt.|
   |**ID**|Legt den Ressourcenbezeichner fest.<br/><br/>Um ein Bild weist Microsoft Visual Studio standardmäßig den nächsten verfügbaren Bezeichner in einer Reihe: IDB_BITMAP1 IDB_BITMAP2 und So weiter. Ähnliche Namen werden für Symbole und Cursor verwendet.|
   |**Palette**|Ändert die Farbeigenschaften.<br/><br/>Doppelklicken Sie auf eine Farbe auswählen und Anzeigen der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben.|
   |**SaveCompressed**|Gibt an, ob das Bild in einem komprimierten Format ist. Diese Eigenschaft ist schreibgeschützt.<br/><br/>Visual Studio können Sie zum Speichern von Bildern in einem komprimierten Format keine damit für alle Bilder, die in Visual Studio erstellt wird, diese Eigenschaft wird **"false"**. Wenn Sie ein komprimiertes Bild (erstellt in einem anderen Programm) in Visual Studio öffnen, wird diese Eigenschaft **"true"**. Wenn Sie ein komprimiertes Bild mithilfe von Visual Studio speichern, werden nicht komprimiert, und diese Eigenschaft wird auf zurückgesetzt **"false"**.|
   |**Width**|Legt die Breite des Bilds (in Pixel) fest. Der Standardwert für Bitmaps gleich 48.<br/><br/>Das Bild ist beschnitten, oder ein leerer Bereich rechts neben das bestehende Image hinzugefügt.|

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
[Vorgehensweise: Erstellen eines Symbols oder anderen Bilds](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Vorgehensweise: Verwenden eines Zeichentools](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Vorgehensweise: Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>