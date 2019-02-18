---
title: 'Vorgehensweise: Erstellen eines Symbols oder anderen Bilds'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
- vc.editors.image.editing
- vc.editors.image.editing
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
- New <Device> Image Type dialog box [C++]
- Custom Image dialog box [C++]
- Open <Device> Image dialog box [C++]
- New Device Image command
- display devices [C++], adding images
- cursors [C++], adding
- icons, adding
- display devices [C++], copying images
- cursors [C++], copying
- icons, copying
- cursors [C++], deleting
- display devices [C++], deleting device image
- icons, erasing
- icons, deleting
- cursors [C++], undoing changes
- icons, undoing changes
- cursors [C++], screen regions
- inverse colors [C++], device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices [C++], transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects [C++], transparent images
- icons [C++], screen regions
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
- colors [C++], icons and cursors
- color palettes, 256-color
- palettes, 256-color
- cursors [C++], hot spots
- hot spots
- .gif files [C++], saving bitmaps as
- jpg files [C++], saving bitmaps as
- jpeg files [C++], saving bitmaps as
- .jpg files [C++], saving bitmaps as
- Image editor [C++], converting image formats
- gif files [C++], saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files [C++], saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
- images [C++], stand-alone editing
- Image editor [C++], converting image formats
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
ms.openlocfilehash: 69fffc71a7b5dfad12e70a9132fc61b11a0914cc
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336591"
---
# <a name="how-to-create-an-icon-or-other-image"></a>Vorgehensweise: Erstellen eines Symbols oder anderen Bilds

Sie können ein neues Image (Bitmap, Symbol, Cursor oder Symbolleiste) erstellen und dann die bildbearbeitung verwenden, um ihre Darstellung anzupassen. Sie können auch eine neue Bitmap Standardressource erstellen eine [Vorlage](../windows/how-to-use-resource-templates.md).

## <a name="icons-and-cursors-image-resources-for-display-devices"></a>Symbole und Cursor: Bildressourcen für Anzeigegeräte

Symbole und Cursor sind grafische Ressourcen, die mehrere Bilder in verschiedenen Größen und Farbschemas für verschiedene Arten von Anzeigegeräten enthalten können. Darüber hinaus weist ein Cursor einen "Hotspot" auf den Speicherort verwendeten Windows zum Nachverfolgen seiner Position. Sowohl Symbole und Cursor werden erstellt und bearbeitet, mithilfe der **Image** -Editor wie Bitmaps und andere Bilder auch.

Bei der Erstellung eines neuen Symbols oder Cursors, der **Image** Editor erstellt zunächst ein Bild eines Standardtyps. Das Bild ist anfänglich mit der Bildschirmfarbe (transparent) gefüllt. Wenn es sich bei dem Bild um einen Cursor handelt, befindet sich der Hotspot anfangs in der oberen linken Ecke (Koordinaten 0,0).

In der Standardeinstellung die **Image** -Editor unterstützt die Erstellung weiterer Bilder für die Geräte, die in der folgenden Tabelle gezeigt. Sie können Bilder für andere Geräte erstellen, indem Sie im Dialogfeld [Benutzerdefiniertes Bild](custom-image-dialog-box-image-editor-for-icons.md)die Parameter für Breite, Höhe und Anzahl der Farben eingeben.

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

|Farbe|Breite (in Pixel)|Höhe (in Pixel)|
|-----------|----------------------|-----------------------|
|Monochrom|16|16|
|Monochrom|32|32|
|Monochrom|48|48|
|Monochrom|64|64|
|Monochrom|96|96|
|16|16|16|
|16|32|32|
|16|64|64|
|16|48|48|
|16|96|96|
|256|16|16|
|256|32|32|
|256|48|48|
|256|64|64|
|256|96|96|

### <a name="create-a-device-image-icon-or-cursor"></a>Erstellen eines gerätebilds (Symbol oder Cursor)

Bei der Erstellung ein neues Symbol oder Cursor-Ressource, die **Image** Editor erstellt zunächst ein Image eines bestimmten Formats (32 × 32, 16 Farben für Symbole und 32 × 32, Monochrom für Cursor). Sie können dann Hinzufügen von Bildern in verschiedenen Größen und Formate zu dem ersten Symbol oder Cursor und jedes zusätzliche Image Bedarf bearbeiten, für die verschiedenen Anzeigegeräten. Sie können auch ein Bild mit einem Ausschneiden und Einfügen-Vorgang aus einem vorhandenen Imagetyp oder aus einer Bitmap in einem Grafikprogramm erstellte bearbeiten.

Beim Öffnen der Ressource Symbol oder Cursor in die [bildbearbeitung](../windows/image-editor-for-icons.md), das Bild, das das aktuelle Anzeigegerät am ehesten entspricht, wird standardmäßig geöffnet.

Die **neu &lt;Gerät&gt; Bildtyp** Dialogfeld können Sie ein neues Gerätebild eines angegebenen Typs erstellt. Zum Öffnen der **neu \<Gerät > Image** wählen Sie im Dialogfeld **Neuer Bildtyp** auf die **Image** im Menü. Die folgenden Eigenschaften enthalten sind **Image Zieltyp** und **benutzerdefinierte**.

Die **Image Zieltyp** -Eigenschaft listet die verfügbaren imagetypen. Wählen Sie den Image-Typ, die, den Sie öffnen möchten:

||||
|-|-|-|
|– 16 x 16, 16 Farben|-48 x 48, 16 Farben|-96 x 96, 16 Farben|
|– 16 x 16, 256 Farben|-48 x 48, 256 Farben|-96 x 96, 256 Farben|
|- 16 x 16, Monochrome|-48 x 48, Monochrom|-96 x 96, Monochrom|
|-32 x 32, 16 Farben|-64 x 64-16 Farben||
|-32 x 32, 256 Farben|-64 x 64, 256 Farben||
|-32 x 32, Monochrom|-64 x 64, Monochrom||

> [!NOTE]
> Alle vorhandenen Bilder werden in dieser Liste nicht angezeigt werden.

Die **benutzerdefinierte** Eigenschaft öffnet die **benutzerdefiniertes Image** Dialogfeld, in dem Sie ein neues Image mit einer benutzerdefinierten Größe und Anzahl der Farben erstellen können.

Die **benutzerdefiniertes Image** Dialogfeld können Sie ein neues Image mit einer benutzerdefinierten Größe und Anzahl der Farben zu erstellen. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Width**|Dient zur Eingabe der Breite des benutzerdefinierten Images in Pixel (1-512, Max. 2048).|
|**Height**|Dient zur Eingabe der Höhe für das benutzerdefinierte Image in Pixel (1-512, Max. 2048).|
|**Farben**|Ein Eingabefeld für die Anzahl der Farben für das benutzerdefinierte Image auswählen: 2, 16 und 256.|

Verwenden der **öffnen &lt;Gerät&gt; Image** Dialogfeld zum Öffnen von Gerätebildern in C++-Projekten. Vorhandene Images mit der Geräte in der aktuellen Ressourcendatei (Bilder, die Teil der aktuellen Ressource) aufgeführt. Die folgende Eigenschaft enthalten ist:

|Eigenschaft|Beschreibung|
|---|---|
|**Aktuellen Images**|Listet die Images, die in der Ressource enthalten. Wählen Sie den Image-Typ, die, den Sie öffnen möchten.|

#### <a name="to-create-a-new-icon-or-cursor"></a>Erstellen Sie ein neues Symbol oder cursor

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn Ihr Projekt noch keine RC-Datei enthält, finden Sie unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**. Für Symbole erstellt diese Aktion eine Symbolressource mit 32 × 32 Pixel, 16 Farben. Bei Cursorn 32 × 32 Pixel, wird die Monochrome (2 Farben)-Abbild erstellt.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

### <a name="to-add-an-image-for-a-different-display-device"></a>Hinzufügen eines Bilds für ein anderes Anzeigegerät

1. Auf der **Image** , wählen Sie im Menü **neues Gerätebild** (oder mit der rechten Maustaste die **Bildbearbeitung** Bereich, und wählen Sie **neues Gerätebild** aus der Kontextmenü).

1. Wählen Sie den Typ des Bilds, die Sie hinzufügen möchten. Sie können auch auswählen, **benutzerdefinierte** Erstellen eines Symbols, dessen Größe nicht in der Standardliste zur Verfügung.

### <a name="to-copy-a-device-image"></a>Kopieren ein Gerätebildes

1. Auf der **Image** , wählen Sie im Menü **Bildtyp öffnen** , und wählen Sie ein Image aus der aktuellen Images aus. Wählen Sie beispielsweise ein Symbol mit 32 × 32 Pixel, 16 Farben.

1. Kopieren Sie das aktuell angezeigte Symbolbild (**STRG**+**C**).

1. Öffnen Sie ein anderes Bild des Symbols in einer anderen **Bildbearbeitung** Fenster. Öffnen Sie z. B. 16 × 16 Pixel und 16 Farben-Version des Symbols.

1. Fügen Sie das Symbolbild (**STRG**+**V**) von einem **Bildbearbeitung** Fenster in den anderen. Wenn Sie eine größere Größe in eine kleinere Größe einfügen, können Sie die Ziehpunkte des Symbols, zum Ändern der Bildgröße.

### <a name="to-delete-a-device-image"></a>Löschen ein Gerätebildes

Während das Symbolbild, in angezeigt wird der **Image** -Editor wählen **Bildtyp löschen** aus der **Image** im Menü. Wenn Sie das letzte Symbol-Abbild in der Ressource löschen, wird die Ressource ebenfalls gelöscht.

   > [!NOTE]
   > Beim Drücken der **Del** Schlüssel, der Bilder und Farben, die Sie haben auf ein Symbol gezeichnet werden gelöscht, bleibt das Symbol, jedoch können Sie jetzt diese Umgestalten. Wenn Sie drücken **Del** versehen, können Sie durch Drücken **STRG**+**Z** , rückgängig gemacht werden.

### <a name="to-create-transparent-or-inverse-regions-in-device-images"></a>Zum Erstellen transparenter oder invertierter Bereiche in Gerätebildern

In der [bildbearbeitung](../windows/image-editor-for-icons.md), das erste Symbol oder Cursor Abbild ein transparent Attribut aufweist. Obwohl das Symbol und der Cursor rechteckigen sind, nicht viele angezeigt, da Teile des Bilds transparent sind; der zugrunde liegenden Bildes auf dem Bildschirm zeigt durch das Symbol oder Cursor. Wenn Sie ein Symbol ziehen, möglicherweise Teile des Bilds in eine invertierte Farbe angezeigt. Sie erstellen diese Auswirkungen durch Festlegen der Bildschirmfarbe und invertierte Farbe in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).

Die Bildschirm- und invertierte Farben, die Sie auf die Symbole anwenden und Cursor entweder Form und Farbe des abgeleiteten Bildes oder umgekehrte Bereiche zuweisen. Teile des Bilds, die diese Attribute geben Sie die Farben an. Sie können die Farben ändern, die die Attribute Fensterfarbe und Inverse Farbe im Bearbeitungsmodus darstellen. Diese Änderungen wirken sich nicht auf die Darstellung des Symbols oder Cursors in Ihrer Anwendung aus.

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der **Hilfe** beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

#### <a name="to-create-transparent-or-inverse-regions"></a>Erstellen transparenter oder invertierter Bereiche

1. In der **Farben** wählen Sie im Fenster der **Fensterfarbe** Auswahl oder das **Inverse Farbe** Selektor.

1. Wenden Sie den Bildschirm oder eine invertierte Farbe auf Ihrem Image mithilfe eines Tools zeichnen. Weitere Informationen zum Zeichnen des Tools finden Sie unter [mithilfe eines Tools zeichnen](using-a-drawing-tool-image-editor-for-icons.md).

#### <a name="to-change-the-screen-or-inverse-color"></a>So ändern Sie den Bildschirm oder Inverse Farbe

1. Wählen Sie entweder die **Fensterfarbe** Auswahl oder das **Inverse Farbe** Selektor.

1. Wählen Sie eine Farbe aus der **Farben** Palette in der **Farben** Fenster.

   Die Komplementärfarbe wird automatisch für die andere zugewiesen.

   > [!TIP]
   > Doppelklicken auf die **Fensterfarbe** oder **Inverse Farbe** Auswahl der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) angezeigt wird.

### <a name="use-the-256-color-palette"></a>Verwenden der 256-Farben-palette

Mithilfe der **Image** -Editor, Symbolen und Cursorn können mit einem 256-Farben-Palette zur Auswahl groß (64 × 64) angepasst werden. Nach dem Erstellen der Ressource wird ein Stil für das Gerät ausgewählt.

#### <a name="to-create-a-256-color-icon-or-cursor"></a>Erstellen eines 256-Farben-Symbols oder Cursors

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**.

1. Auf der **Image** , wählen Sie im Menü **neues Gerätebild**.

1. Wählen Sie die gewünschte Formatvorlage für das Bild mit 256 Farben.

#### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Wählen Sie eine Farbe aus der 256-Farben-Palette für große Symbole

Um mit einer Auswahl aus der 256-Farben-Palette zu zeichnen, müssen Sie die Farben auswählen der **Farben** Palette in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).

1. Wählen Sie die große Symbole oder Cursor, oder erstellen Sie eine neue große Symbole oder Cursor.

1. Wählen Sie eine Farbe aus der 256 Farben der **Farben** Palette in der **Farben** Fenster.

   Die ausgewählte Farbe wird die aktuelle Farbe in der **Farben** Palette in der **Farben** Fenster.

   > [!NOTE]
   > Die anfängliche Palette verwendet für 256-Farben-Images entspricht die Palette von zurückgegebenen der `CreateHalftonePalette` Windows-API. Alle Symbole, die für die Windows-Shell vorgesehen, sollten diese Palette verwenden, um Flimmern während der Realisierung der Palette zu vermeiden.

### <a name="set-a-cursor39s-hot-spot"></a>Legen Sie einen Cursor&#39;Hotspot s

Die Hotspots eines Cursors ist der Punkt, auf die Windows verweist, in die Position des Cursors nachverfolgen. Standardmäßig wird den Hotspot auf der linken oberen Ecke des Cursors (Koordinaten 0,0) festgelegt. Die **Hotspot** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zeigt die Koordinaten des HotSpot.

#### <a name="to-set-a-cursors-hot-spot"></a>Festlegen des Hotspots eines Cursors

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), wählen Sie die **Hotspot festlegen** Tool.

1. Wählen Sie das Pixel, die, das Sie als den Cursorhotspot zuweisen möchten.

   Die **Hotspot** -Eigenschaft in der **Eigenschaften** Fenster zeigt die neuen Koordinaten.

   > [!TIP]
   > Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

## <a name="saving-bitmaps-as-gifs-or-jpegs"></a>Speichern von Bitmaps als GIFs oder JPEGs

Wenn Sie eine Bitmap zu erstellen, wird das Bild im Bitmapformat (BMP) erstellt. Sie können jedoch das Image als GIF- oder JPEG oder in anderen Grafikformaten speichern.

> [!NOTE]
> Dieser Prozess gilt nicht für Symbole und Cursor.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Zum Erstellen und speichern eine Bitmap als GIF- oder JPEG

1. Von der **Datei** Menü wählen **öffnen**, und wählen Sie dann **Datei**.

1. In der **neuen Dateidialogfeld**, wählen Sie die **Visual C++** Ordner, wählen Sie dann **Bitmapdatei (BMP)** in der **Vorlagen** und wählen Sie  **Open**.

   Die Bitmap wird im der **Image** Editor.

1. Nehmen Sie Änderungen an der neuen Bitmap, je nach Bedarf.

1. Mit der Bitmap, die noch geöffnet, in der **Image** -Editor, wählen Sie **speichern *Filename*BMP als** auf die **Datei** im Menü.

1. In der **Datei speichern unter** Dialogfeld Geben Sie den Namen, erhalten die Datei und die Erweiterung, die das Dateiformat gibt an, Sie in möchten, sollen, die **Dateiname** Feld. Z. B. *: MeineDatei.gif*.

   > [!NOTE]
   > Sie müssen erstellen oder öffnen die Bitmap außerhalb des Projekts, um ihn als ein anderes Dateiformat zu speichern. Wenn Sie beim Erstellen oder öffnen Sie diese in Ihrem Projekt die **speichern** Befehl nicht verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

1. Klicken Sie auf **Speichern**.

## <a name="converting-an-image-from-one-format-to-another"></a>Konvertieren von Bildern in andere Formate

Sie öffnen können, GIF- oder JPEG-Bilder in der **Image** Editor und speichern Sie sie als Bitmaps. Darüber hinaus können Sie eine Bitmap-Datei zu öffnen und speichern Sie ihn als GIF- oder JPEG. Sie arbeiten mit Images müssen nicht Teil eines Projekts für die Bearbeitung in der Entwicklungsumgebung sein (finden Sie unter [unabhängig bearbeiten](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)).

### <a name="to-convert-an-image-from-one-format-to-another"></a>Um ein Image von einem Format in eine andere zu konvertieren.

1. Öffnen Sie das Abbild in der **Image** Editor.

1. Von der **Datei** Menü wählen **speichern *Filename* als**.

1. In der **Datei speichern unter** Dialogfeld die **Dateiname** geben den Dateinamen und die Erweiterung ein, das Format angezeigt werden sollen.

1. Klicken Sie auf **Speichern**.

## <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Beim Hinzufügen einer neuen imageressource zu einem nicht verwalteten C++-Projekt

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können einfach mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md), wählen Sie den Typ der Bildressource, die Sie erstellen möchten (**Bitmap**, z. B.) Wählen Sie dann **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

## <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Beim Hinzufügen einer neuen imageressource zu einem Projekt in einer Programmiersprache.

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in des Projektordners (z. B. `WindowsApplication1`).

1. Wählen Sie im Kontextmenü den Befehl **hinzufügen**, wählen Sie dann **neues Element hinzufügen**.

1. In der **Kategorien** Bereich, erweitern Sie die **Lokale Projektelemente** Ordner, wählen Sie dann **Ressourcen**.

1. In der **Vorlagen** Bereich, wählen Sie den Ressourcentyp, die Sie Ihrem Projekt hinzufügen möchten.

   Die Ressource wird hinzugefügt, um das Projekt im **Projektmappen-Explorer** und die Ressource wird geöffnet, der [bildbearbeitung](../windows/image-editor-for-icons.md). Sie können nun alle Tools zur Verfügung, in dem Bild-Editor verwenden, so ändern Sie Ihr Image. Weitere Informationen zum Hinzufügen von Bildern zu einem verwalteten Projekt finden Sie unter [Laden eines Bildes zur Entwurfszeit](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

   > [!NOTE]
   > Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt. Weitere Informationen finden Sie unter [Erstellen von Ressourcendateien](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Konvertieren von Bitmaps in Symbolleisten](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Erstellen neuer Symbolleisten](../windows/creating-new-toolbars.md)<br/>
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
[Menü "Bild"](../windows/image-menu-image-editor-for-icons.md)<br/>
[Symbole](/windows/desktop/menurc/icons)<br/>
[Cursor](/windows/desktop/menurc/cursors)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>