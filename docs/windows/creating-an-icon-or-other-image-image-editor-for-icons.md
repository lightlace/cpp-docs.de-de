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
ms.openlocfilehash: 92eac69e6802a824c4b6e107d2ff3393e931a542
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563055"
---
# <a name="how-to-create-an-icon-or-other-image"></a>Vorgehensweise: Erstellen eines Symbols oder anderen Bilds

Sie können ein neues Image, Bitmap, Symbol, Cursor, oder der Symbolleiste zu erstellen, und dann die **Bildbearbeitung** um ihre Darstellung anzupassen. Sie können auch eine neue Bitmap Standardressource erstellen eine [Ressourcenvorlage](../windows/how-to-use-resource-templates.md).

## <a name="icons-and-cursors-image-resources-for-display-devices"></a>Symbole und Cursor: Bildressourcen für Anzeigegeräte

Symbole und Cursor sind grafische Ressourcen, die mehrere Bilder in verschiedenen Größen und Farbschemas für verschiedene Arten von Anzeigegeräten enthalten können. Ein Cursor verfügt auch über einen Hotspot, der Speicherort Windows zum Nachverfolgen seiner Position verwendet. Sowohl Symbole und Cursor werden erstellt und bearbeitet, mithilfe der **Bildbearbeitung**, wie Bitmaps und andere Bilder auch.

Bei der Erstellung eines neuen Symbols oder Cursors, der **Bildbearbeitung** erstellt zunächst ein Bild eines Standardtyps. Das Bild ist anfänglich mit der Bildschirmfarbe (transparent) gefüllt. Wenn das Bild eines Cursors ist, den Hotspot ist anfänglich mit den Koordinaten der oberen linken Ecke `0,0`.

In der Standardeinstellung die **Bildbearbeitung** unterstützt die Erstellung weiterer Bilder für die Geräte, die in der folgenden Tabelle gezeigt. Sie können Bilder für andere Geräte erstellen, geben Sie die Breite, Höhe und Anzahl der Farben Parameter in der **benutzerdefiniertes Image** Dialogfeld.

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

Bei der Erstellung ein neues Symbol oder Cursor-Ressource, die **Bildbearbeitung** erstellt zunächst ein Image eines bestimmten Formats (32 × 32, 16 Farben für Symbole und 32 × 32, Monochrom für Cursor). Sie können dann Hinzufügen von Bildern in verschiedenen Größen und Formate zu dem ersten Symbol oder Cursor und jedes zusätzliche Image Bedarf bearbeiten, für die verschiedenen Anzeigegeräten. Sie können auch ein Bild mit einem Ausschneiden und Einfügen-Vorgang aus einem vorhandenen Imagetyp oder aus einer Bitmap in einem Grafikprogramm erstellte bearbeiten.

Beim Öffnen der Ressource Symbol oder Cursor in die [Bildbearbeitung](../windows/image-editor-for-icons.md), das Bild, das das aktuelle Anzeigegerät am ehesten entspricht, wird standardmäßig geöffnet.

> [!NOTE]
> Wenn Ihr Projekt noch keine RC-Datei enthält, finden Sie unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

Die **neu &lt;Gerät&gt; Bildtyp** Dialogfeld können Sie ein neues Gerätebild eines angegebenen Typs erstellt. Zum Öffnen der **neu \<Gerät > Image** (Dialogfeld), wechseln Sie zum Menü **Image** > **Neuer Bildtyp**. Die folgenden Eigenschaften enthalten sind **Image Zieltyp** und **benutzerdefinierte**.

Die **Image Zieltyp** -Eigenschaft listet die verfügbaren imagetypen, die in dem Sie das Image auswählen geben, die Sie öffnen möchten:

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

1. In [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources), mit der rechten Maustaste Ihre *RC* -Datei, und wählen Sie **Ressource einfügen**. Wenn Sie eine vorhandene imageressource bereits in haben Ihrer *RC* -Datei, z. B. einen Cursor, Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen**.

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**. Für Symbole erstellt diese Aktion eine Symbolressource mit 32 × 32 Pixel, 16 Farben. Bei Cursorn 32 × 32 Pixel, wird die Monochrome (2 Farben)-Abbild erstellt.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

### <a name="to-add-an-image-for-a-different-display-device"></a>Hinzufügen eines Bilds für ein anderes Anzeigegerät

1. Wechseln Sie zum Menü **Image** > **neues Gerätebild**, oder mit der rechten Maustaste den **Bildbearbeitung** Bereich, und wählen Sie **neues Gerätebild**.

1. Wählen Sie den Typ des Bilds, die Sie hinzufügen möchten. Sie können auch auswählen, **benutzerdefinierte** Erstellen eines Symbols, dessen Größe nicht in der Standardliste zur Verfügung.

### <a name="to-copy-a-device-image"></a>Kopieren ein Gerätebildes

1. Wechseln Sie zum Menü **Image** > **Bildtyp öffnen** , und wählen Sie ein Image aus der aktuellen Images aus. Wählen Sie beispielsweise ein Symbol mit 32 × 32 Pixel, 16 Farben.

1. Kopieren Sie das aktuell angezeigte Symbolbild (**STRG**+**C**).

1. Öffnen Sie ein anderes Bild des Symbols in einer anderen **Bildbearbeitung** Fenster. Öffnen Sie z. B. 16 × 16 Pixel und 16 Farben-Version des Symbols.

1. Fügen Sie das Symbolbild (**STRG**+**V**) von einem **Bildbearbeitung** Fenster in den anderen. Wenn Sie eine größere Größe in eine kleinere Größe einfügen, können Sie die Ziehpunkte des Symbols, zum Ändern der Bildgröße.

### <a name="to-delete-a-device-image"></a>Löschen ein Gerätebildes

Während das Symbolbild, in angezeigt wird der **Bildbearbeitung**, navigieren Sie zum Menü **Image** > **Bildtyp löschen**. Wenn Sie das letzte Symbol-Abbild in der Ressource löschen, wird die Ressource ebenfalls gelöscht.

> [!NOTE]
> Beim Drücken der **Del** drücken, Bildern und Farben, die Sie auf ein Symbol gezeichnet haben werden gelöscht, jedoch bleibt das Symbol und Sie können jetzt Umgestalten. Wenn Sie drücken **Del** versehentlich, drücken Sie **STRG**+**Z** , rückgängig gemacht werden.

### <a name="to-create-transparent-or-inverse-regions-in-device-images"></a>Zum Erstellen transparenter oder invertierter Bereiche in Gerätebildern

In der [Bildbearbeitung](../windows/image-editor-for-icons.md), das erste Symbol oder Cursor Abbild ein transparent Attribut aufweist. Obwohl das Symbol und der Cursor rechteckigen sind, nicht viele angezeigt, da Teile des Bilds transparent sind, und der zugrunde liegenden Bildes auf dem Bildschirm durch das Symbol oder Cursor zeigt. Wenn Sie ein Symbol ziehen, möglicherweise Teile des Bilds in eine invertierte Farbe angezeigt. Sie erstellen diese Auswirkungen durch Festlegen der Bildschirmfarbe und invertierte Farbe in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).

Die Bildschirm- und invertierte Farben, die Sie auf die Symbole anwenden und Cursor entweder Form und Farbe des abgeleiteten Bildes oder umgekehrte Bereiche zuweisen. Teile des Bilds, die diese Attribute geben Sie die Farben an. Sie können die Farben ändern, die die Attribute Fensterfarbe und Inverse Farbe im Bearbeitungsmodus darstellen. Diese Änderungen wirken sich nicht auf die Darstellung des Symbols oder Cursors in Ihrer Anwendung aus.

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der **Hilfe** beschriebenen. Um Ihre Einstellungen zu ändern, wechseln Sie zum Menü **Tools** > **Einstellungen importieren und exportieren**. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

#### <a name="to-create-transparent-or-inverse-regions"></a>Erstellen transparenter oder invertierter Bereiche

1. In der **Farben** Fenster, wählen Sie im Auswahlbereich **Fensterfarbe** oder **Inverse Farbe**.

1. Wenden Sie den Bildschirm oder eine invertierte Farbe auf Ihrem Image mithilfe eines Tools zeichnen. Weitere Informationen zum Zeichnen des Tools finden Sie unter [mithilfe eines Tools zeichnen](using-a-drawing-tool-image-editor-for-icons.md).

#### <a name="to-change-the-screen-or-inverse-color"></a>So ändern Sie den Bildschirm oder Inverse Farbe

1. Wählen Sie entweder die **Fensterfarbe** Auswahl oder das **Inverse Farbe** Selektor.

1. Wählen Sie eine Farbe aus der **Farben** Palette in der **Farben** Fenster.

   Die Komplementärfarbe wird automatisch für die andere zugewiesen.

   > [!TIP]
   > Doppelklicken auf die **Fensterfarbe** oder **Inverse Farbe** Auswahl der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) angezeigt wird.

### <a name="use-the-256-color-palette"></a>Verwenden der 256-Farben-palette

Mithilfe der **Bildbearbeitung**, Symbole und Cursor aus mit einem 256-Farben-Palette auswählen große (64 × 64) angepasst werden können. Nach dem Erstellen der Ressource wird ein Stil für das Gerät ausgewählt.

#### <a name="to-create-a-256-color-icon-or-cursor"></a>Erstellen eines 256-Farben-Symbols oder Cursors

1. In [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources), mit der rechten Maustaste Ihre *RC* -Datei, und wählen Sie **Ressource einfügen**. Wenn Sie eine vorhandene imageressource bereits in haben Ihrer *RC* -Datei, z. B. einen Cursor, Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen**.

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**.

1. Wechseln Sie zum Menü **Image** > **neues Gerätebild** , und wählen Sie die gewünschten 256-Farben-Image-Format.

#### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Wählen Sie eine Farbe aus der 256-Farben-Palette für große Symbole

Um mit einer Auswahl aus der 256-Farben-Palette zu zeichnen, müssen Sie die Farben auswählen der **Farben** Palette in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).

1. Wählen Sie die große Symbole oder Cursor, oder erstellen Sie eine neue große Symbole oder Cursor.

1. Wählen Sie eine Farbe aus der 256 Farben der **Farben** Palette in der **Farben** Fenster.

   Die ausgewählte Farbe wird die aktuelle Farbe in der **Farben** Palette in der **Farben** Fenster.

   > [!NOTE]
   > Die anfängliche Palette verwendet für 256-Farben-Images entspricht die Palette von zurückgegebenen der `CreateHalftonePalette` Windows-API. Alle Symbole, die für die Windows-Shell vorgesehen, sollten diese Palette verwenden, um Flimmern während der Realisierung der Palette zu vermeiden.

### <a name="to-set-a-cursors-hot-spot"></a>Festlegen des Hotspots eines Cursors

Die Hotspots eines Cursors ist der Punkt, auf die Windows verweist, in die Position des Cursors nachverfolgen. In der Standardeinstellung den Hotspot festgelegt ist, klicken Sie auf der linken oberen Ecke des Cursors mit Koordinaten `0,0`. Die **Hotspot** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zeigt die Koordinaten des HotSpot.

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), wählen Sie die **Hotspot festlegen** Tool.

1. Wählen Sie das Pixel, die, das Sie als den Cursorhotspot zuweisen möchten.

   Die **Hotspot** -Eigenschaft in der **Eigenschaften** Fenster zeigt die neuen Koordinaten.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Zum Erstellen und speichern eine Bitmap als GIF- oder JPEG

Wenn Sie eine Bitmap zu erstellen, wird das Bild im Bitmapformat (BMP) erstellt. Sie können jedoch das Image als GIF- oder JPEG oder in anderen Grafikformaten speichern.

> [!NOTE]
> Dieser Prozess gilt nicht, Symbole und Cursor.

1. Wechseln Sie zum Menü **Datei** > **öffnen**, und wählen Sie dann **Datei**.

1. In der **neuen Dateidialogfeld**, wählen Sie die **Visual C++** Ordner, wählen Sie dann **Bitmapdatei (BMP)** in der **Vorlagen** und wählen Sie  **Open**.

   Die Bitmap wird im der **Bildbearbeitung**.

1. Nehmen Sie Änderungen an der neuen Bitmap, je nach Bedarf.

1. Mit der Bitmap, die noch geöffnet, in der **Bild-Editor**, navigieren Sie zum Menü **Datei** > **speichern *Filename*BMP als**.

1. In der **Datei speichern unter** Dialogfeld Geben Sie den Namen, erhalten die Datei und die Erweiterung, die das Dateiformat gibt an, Sie in möchten, sollen, die **Dateiname** Feld. Z. B. *: MeineDatei.gif*.

   > [!NOTE]
   > Sie müssen erstellen oder öffnen die Bitmap außerhalb des Projekts, um ihn als ein anderes Dateiformat zu speichern. Wenn Sie beim Erstellen oder öffnen Sie diese in Ihrem Projekt die **speichern** Befehl nicht verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

1. Klicken Sie auf **Speichern**.

### <a name="to-convert-an-image-from-one-format-to-another"></a>Um ein Image von einem Format in eine andere zu konvertieren.

Sie öffnen können, GIF- oder JPEG-Bilder in der **Bildbearbeitung** und speichern Sie sie als Bitmaps. Darüber hinaus können Sie eine Bitmap-Datei zu öffnen und speichern Sie ihn als GIF- oder JPEG. Sie arbeiten mit Images müssen nicht Teil eines Projekts für die Bearbeitung in der Entwicklungsumgebung sein (finden Sie unter [unabhängig bearbeiten](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)).

1. Öffnen Sie das Abbild in der **Bildbearbeitung**.

1. Wechseln Sie zum Menü **Datei** > **speichern *Filename* als**.

1. In der **Datei speichern unter** Dialogfeld die **Dateiname** geben den Dateinamen und die Erweiterung ein, das Format angezeigt werden sollen.

1. Klicken Sie auf **Speichern**.

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Beim Hinzufügen einer neuen imageressource zu einem nicht verwalteten C++-Projekt

1. In [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources), mit der rechten Maustaste Ihre *RC* -Datei, und wählen Sie **Ressource einfügen**. Wenn Sie eine vorhandene imageressource bereits in haben Ihrer *RC* -Datei, z. B. einen Cursor, Sie können einfach mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen**.

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md), wählen Sie den Typ der Bildressource, die Sie erstellen möchten (**Bitmap**, z. B.) Wählen Sie dann **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Beim Hinzufügen einer neuen imageressource zu einem Projekt in einer Programmiersprache.

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in des Projektordners (z. B. *WindowsApplication1*).

1. Wählen Sie im Kontextmenü den Befehl **hinzufügen**, wählen Sie dann **neues Element hinzufügen**.

1. In der **Kategorien** Bereich, erweitern Sie die **Lokale Projektelemente** Ordner, wählen Sie dann **Ressourcen**.

1. In der **Vorlagen** Bereich, wählen Sie den Ressourcentyp, die Sie Ihrem Projekt hinzufügen möchten.

   Die Ressource wird hinzugefügt, um das Projekt im **Projektmappen-Explorer** und die Ressource wird geöffnet, der [Bildbearbeitung](../windows/image-editor-for-icons.md). Können Sie jetzt alle Tools zur Verfügung, in der **Bildbearbeitung** so ändern Sie Ihr Image. Weitere Informationen zum Hinzufügen von Bildern zu einem verwalteten Projekt finden Sie unter [Laden eines Bildes zur Entwurfszeit](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
[Vorgehensweise: Bearbeiten eines Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Vorgehensweise: Verwenden eines Zeichentools](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Vorgehensweise: Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
<!--
[Converting Bitmaps to Toolbars](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Creating New Toolbars](../windows/creating-new-toolbars.md)<br/>
[Icons](/windows/desktop/menurc/icons)<br/>
[Cursors](/windows/desktop/menurc/cursors)<br/>-->