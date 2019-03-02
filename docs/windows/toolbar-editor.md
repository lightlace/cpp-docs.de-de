---
title: Symbolleisten-Editor (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.toolbar.F1
- vc.editors.toolbar
- vc.editors.newtoolbarresource
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
- tool tips [C++], adding to toolbar buttons
- "\n in tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: 5aadb00e6e010467ee9c70dc357916d3c4f81853
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211081"
---
# <a name="toolbar-editor-c"></a>Symbolleisten-Editor (C++)

Die **Symbolleisten-Editor** können Sie Symbolleistenressourcen erstellen und Bitmaps in Symbolleistenressourcen konvertieren. Die **Symbolleisten-Editor** verwendet eine grafische Anzeige angezeigt wird, eine Symbolleiste und Schaltflächen, mit denen ähneln, wie sie in einer fertigen Anwendung ansehen.

Die **Symbolleisten-Editor** Fenster zeigt zwei Ansichten eines Schaltflächensymbols an, die identisch mit der **Bildbearbeitung** Fenster. Eine Leiste für geteilte trennt die beiden Bereiche aus, und Sie können die Leiste für geteilte Seite ziehen, rechts, um die relative Größe der Bereiche ändern. Der aktive Bereich einem Markierungsrahmen umgeben und oberhalb der beiden Ansichten des Bilds wird die betreffende Symbolleiste.

![Symbolleisten-Editor](../mfc/media/vctoolbareditor.gif "VcToolbarEditor")<br/>
**Symbolleisten-Editor**

Die **Symbolleisten-Editor** ist vergleichbar mit der **Bildbearbeitung** in Funktionen und die Menüelemente, grafische Tools und Bitmapraster zwischen den beiden sind identisch. Steht der Menübefehl im der **Image** Menü Wechseln der **Symbolleisten-Editor** und die **Bildbearbeitung**. Weitere Informationen zur Verwendung der **Grafiken** Symbolleiste **Farben** Palette, oder **Image** im Menü finden Sie unter [Bild-Editor](../windows/image-editor-for-icons.md).

Sie können eine neue Symbolleiste in einem C++-Projekt erstellen, durch die Konvertierung einer Bitmaps. Die Grafik aus dem Bitmap, die in der Schaltflächenbilder für eine Symbolleiste konvertiert werden. Die Bitmap wird in der Regel mehrere Images von Schaltfläche auf einer einzelnen Bitmap mit einem einzelnen Abbild für jede Schaltfläche enthält. Bilder können eine beliebige Größe sein, wie der Standardwert 16 Pixel breit und die Höhe des Bilds ist. Können Sie angeben, die Größe der Schaltflächenbilder in der **neue Symbolleistenressource** Dialogfeld bei der Auswahl **Symbolleisten-Editor** aus der **Image** Menü während der  **Bild-Editor**.

Die **neue Symbolleistenressource** Dialogfeld können Sie angeben, die Breite und Höhe der Schaltflächen, die Sie für eine Symbolleistenressource in einem C++-Projekt hinzufügen. Der Standardwert ist 16 × 15 Pixel.

Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048, wenn Sie festlegen, also die **Schaltflächenbreite** zu *512*, nur möglich, vier Schaltflächen. Wenn Sie die Breite auf *513*, Sie können nur drei Schaltflächen verwenden.

Die **neue Symbolleistenressource** Dialogfeld hat die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---------------|
|**Schaltflächenbreite**|Dient zur Eingabe von der Breite für das Symbolleisten-Schaltflächen, die Sie aus einer Bitmap-Ressource in einer Symbolleistenressource konvertieren.|
|**Schaltflächenhöhe**|Dient zur Eingabe von der Höhe für die Symbolleisten-Schaltflächen, die Sie aus einer Bitmap-Ressource in einer Symbolleistenressource konvertieren.|

> [!NOTE]
> Die Bilder werden zugeschnitten, um die Breite und Höhe angegeben, und die Farben werden angepasst, um die Farben der Standardsymbolleiste (16 Farben) zu verwenden.

Standardmäßig wird eine neue oder leere Schaltfläche am rechten Ende der Symbolleiste angezeigt. Sie können diese Schaltfläche, verschieben, bevor Sie ihn bearbeiten. Wenn Sie eine neue Schaltfläche erstellen, wird eine andere, leere Schaltfläche rechts neben der bearbeiteten Schaltfläche angezeigt. Wenn Sie eine Symbolleiste speichern, wird die Schaltfläche "leere" nicht gespeichert.

Eine Symbolleisten-Schaltfläche hat die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|**ID**|Definiert die ID für die Schaltfläche. Die Dropdown-Liste enthält allgemeine **ID** Namen.|
|**Width**|Legt die Breite der Schaltfläche fest. 16 Pixel wird empfohlen.|
|**Height**|Legt die Höhe der Schaltfläche fest. Die Höhe einer Schaltfläche ändert sich die Höhe aller Schaltflächen auf der Symbolleiste. 15 Pixel wird empfohlen.|
|**Eingabeaufforderung**|Definiert die Nachricht in der Statusleiste angezeigt. Hinzufügen von *\n* und fügt Sie ein Namen ein **QuickInfo** , Symbolleisten-Schaltfläche. Weitere Informationen finden Sie unter [Erstellen einer QuickInfo](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Breite** und **Höhe** gelten für alle Schaltflächen. Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048, also wenn Sie die Schaltflächenbreite auf *512*, Sie können nur vier Schaltflächen haben und wenn Sie die Breite auf *513*, Sie können nur drei Schaltflächen verwenden.

## <a name="how-to"></a>Gewusst wie

Die **Symbolleisten-Editor** können Sie:

### <a name="to-create-new-toolbars"></a>Zum Erstellen neuer Symbolleisten

1. In **Ressource** anzeigen, mit der rechten Maustaste in der RC-Datei, und wählen Sie **Ressource hinzufügen**. Wenn Sie eine vorhandene Symbolleiste in der RC-Datei verfügen, Sie können mit der rechten Maustaste die **Symbolleiste** Ordner, und wählen **Toolbar einfügen**.

1. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Symbolleiste** in die **Ressourcentyp** Liste aus, und wählen Sie dann **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der **Symbolleiste** Ressourcentyp an, es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>Zum Konvertieren von Bitmaps in Symbolleistenressourcen

1. Öffnen Sie eine vorhandene Bitmapressource in der [Bildbearbeitung](../windows/image-editor-for-icons.md). Wenn die Bitmap nicht bereits in der RC-Datei, mit der rechten Maustaste in der RC-Datei, und wählen Sie **Import**, navigieren Sie dann auf die Bitmap, die Sie verwenden möchten, fügen Sie auf die RC-Datei hinzu, und wählen Sie **öffnen**.

1. Wechseln Sie zum Menü **Image** > **Symbolleisten-Editor**.

   Die **neue Symbolleistenressource** Dialogfeld wird angezeigt. Sie können die Breite und Höhe der Symbolbilder entsprechend die Bitmap ändern. Das Symbolleistenbild ist dann angezeigt, der **Symbolleisten-Editor**.

1. Ändern Sie den Befehl, um die Konvertierung abzuschließen, **ID** der Schaltfläche mit den [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Geben Sie den neuen *ID* oder wählen Sie eine **ID** aus der Dropdown-Liste.

   > [!TIP]
   > Die **Eigenschaften** Fenster enthält eine Stecknadel-Schaltfläche in der Titelleiste an und aktiviert oder deaktiviert die Auswahl dieser **automatisch im Hintergrund** für das Fenster. Um alle Eigenschaften der Symbolleisten-Schaltflächen durchlaufen ohne einzelne Eigenschaft erneut öffnen, aktivieren Sie **automatisch im Hintergrund** deaktiviert daher **Eigenschaften** Fenster stationär bleibt.

   Sie können auch die Befehls-IDs der Schaltflächen auf die neue Symbolleiste ändern, mit der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

### <a name="to-manage-toolbar-buttons"></a>Zum Verwalten von Symbolleisten-Schaltflächen

So erstellen Sie eine neue Symbolleisten-Schaltfläche:

1. In [Ressourcenansicht](../windows/resource-view-window.md) erweitern Sie den Ressourcenordner (z. B. *Projekt1.rc*).

1. Erweitern Sie die **Symbolleiste** Ordner, und wählen Sie eine Symbolleiste zu bearbeiten, führen Sie dann eine der folgenden:

   - Weisen Sie eine ID, auf die leere Schaltfläche am rechten Ende der Symbolleiste. Bearbeiten Sie dazu die **ID** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Beispielsweise empfiehlt es sich um einer Symbolleisten-Schaltfläche, die gleiche ID wie eine Menüoption gewähren. In diesem Fall verwenden Sie im Dropdown-Listenfeld auswählen der **ID** der Menüoption.

   - Wählen Sie die leere Schaltfläche am rechten Ende der Symbolleiste (in der **Symbolleiste anzeigen** Bereich) und Zeichnen zu beginnen. Die Befehls-ID eine Standard-Schaltfläche zugewiesen ist (ID_BUTTON\<n >).

Sie können auch kopieren und fügen Sie ein Image auf einer Symbolleiste als neue Schaltfläche.

So fügen Sie ein Bild als Schaltfläche zu einer Symbolleiste hinzu:

1. In [Ressourcenansicht](../windows/resource-view-window.md), öffnen Sie die Symbolleiste, indem Sie darauf doppelklicken.

1. Öffnen Sie als Nächstes das Bild, das Sie hinzufügen, klicken Sie auf der Symbolleiste möchten.

   > [!NOTE]
   > Wenn Sie das Bild in Visual Studio öffnen, öffnen sie in der **Image** Editor. Sie können das Bild auch in anderen Grafikprogrammen öffnen.

1. Von der **bearbeiten** Menü wählen **Kopie**.

1. Wechseln Sie durch Auswahl einer Registerkarte am oberen Rand der Datenquellen-Fenster auf der Symbolleiste.

1. Von der **bearbeiten** Menü wählen **einfügen**.

   Das Bild wird auf der Symbolleiste als neue Schaltfläche angezeigt.

So verschieben Sie eine Symbolleisten-Schaltfläche:

In der **Symbolleiste anzeigen** Bereich, ziehen Sie die Schaltfläche, die Sie auf der Symbolleiste am neuen Speicherort verschieben möchten.

Halten Sie zum Kopieren von Schaltflächen von einer Symbolleiste die **STRG** Schlüssel und klicken Sie in der **Symbolleiste anzeigen** Bereich, ziehen Sie die Schaltfläche mit den neuen Speicherort auf der Symbolleiste oder an einem Speicherort auf einer anderen Symbolleiste.

Löschen einer Symbolleisten-Schaltfläche, wählen Sie die Symbolleisten-Schaltfläche, und ziehen es aus der Symbolleiste.

Zum Einfügen, oder Entfernen von Leerzeichen zwischen den Schaltflächen einer Symbolleiste aus, entweder ziehen Sie sie aus, oder auf anderen auf der Symbolleiste.

|Aktion|Schritt|
|------|------|
|Ein Leerzeichen vor eine Schaltfläche eingefügt, die gefolgt von einem Leerzeichen ist nicht|Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.|
|Ein Leerzeichen vor eine Schaltfläche eingefügt, die durch ein Leerzeichen folgt und der nachgestellte Leerzeichen zu halten.|Ziehen Sie die Schaltfläche aus, bis am rechten oder unteren Rand die Schaltfläche "Weiter Schaltflächenrand", oder geringfügig überlappt.|
|Fügen Sie ein Leerzeichen vor eine Schaltfläche, die durch ein Leerzeichen folgt, und schließen diese folgenden Speicherplatz|Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.|
|So entfernen Sie ein Leerzeichen zwischen den Schaltflächen einer Symbolleiste|Ziehen Sie die Schaltfläche auf einer Seite des Speicherplatzes auf die Schaltfläche auf der anderen Seite für den Speicherplatz, bis sie die Schaltfläche "Weiter", etwa um die Hälfte überlappt.|

> [!NOTE]
> Wenn kein Platz im Zweifelsfall die Schaltfläche, die Sie ist aus ziehen und Sie ziehen Sie die Schaltfläche hinter die benachbarte Schaltfläche mehr als zur Hälfte der **Symbolleisten-Editor** Fügt ein Leerzeichen auf der entgegengesetzten Seite der Schaltfläche, die Sie ziehen können.

So ändern die Eigenschaften einer Symbolleisten-Schaltfläche:

1. Wählen Sie die Symbolleisten-Schaltfläche in einem C++-Projekt.

1. Geben Sie die neue ID in der **ID** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), oder verwenden Sie die Dropdownliste, wählen Sie ein neues **ID**.

So erstellen Sie eine QuickInfo für eine Symbolleisten-Schaltfläche:

1. Wählen Sie die Symbolleisten-Schaltfläche.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in die **Eingabeaufforderung** Feld, eine Beschreibung der Schaltfläche für die Statusleiste und nach der Nachricht hinzufügen, das Hinzufügen von `\n` und den Namen des Tools Tipp.

Beispielsweise sehen die QuickInfo für die **Drucken** Schaltfläche **WordPad**:

1. Open **WordPad**.

1. Zeigen Sie den Mauszeiger auf die **Drucken** Symbolleisten-Schaltfläche, und beachten Sie, dass das Wort `Print` nun unverankert ist, unter der Maus.

1. Sehen Sie sich die Statusleiste am unteren Rand der **WordPad** Fenster, und beachten Sie, dass es jetzt der Text zeigt `Prints the active document`.

`Print` ist der Name der Tool-Tipps und `Prints the active document` ist die Beschreibung der Schaltfläche für die Statusleiste.

Wenn Sie möchten diesen Effekt mit der **Symbolleisten-Editor**, legen die **Eingabeaufforderung** Eigenschaft `Prints the active document\nPrint`.

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Toolbar Button Properties](../windows/toolbar-button-properties.md)<br/>-->
