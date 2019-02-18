---
title: 'Vorgehensweise: Anordnen von Steuerelementen (C++) | Microsoft-Dokumentation'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.grouping
- vc.editors.dialog.combo
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
- Dialog Editor [C++], guides and margins
- guides, clearing
- guides
- dialog box controls [C++], placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
- guides, disabling snapping
- controls [C++], snap to guides/grid
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
- grid spacing
- guides, settings
- layout grid in Dialog Editor
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls [C++], grouping radio buttons
- grouping controls
- radio buttons [C++], grouping on dialog boxes
- controls [C++], tab order
- focus, tab order
- tab controls [C++], tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls [C++], tab order
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: d9bd73c9cc81b113f222bbc090c62200c93554b2
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336630"
---
# <a name="how-to-arrange-controls-c"></a>Vorgehensweise: Anordnen von Steuerelementen (C++)

Die **Dialogfeld** -Editor bietet Layouttools, ausrichten und Größe von Steuerelementen automatisch. Für die meisten Aufgaben können Sie die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Alle **Dialog-Editor** Symbolleistenbefehle stehen auch in der **Format** haben Sie im Menü, und die meisten [Tastenkombinationen](../windows/accelerator-keys-for-the-dialog-editor.md).

Viele Layoutbefehle für Dialogfelder sind verfügbar, nur, wenn mehr als ein Steuerelement ausgewählt ist. Sie können eine einzelne oder mehrere Steuerelemente auswählen, und wenn mehr als ein Steuerelement ausgewählt ist, das erste Objekt, das Sie auswählen, wird standardmäßig "dominanten" Steuerelements. Informationen zum Auswählen von Steuerelementen und das dominante Steuerelement, finden Sie unter [Markieren von Steuerelementen](../windows/selecting-controls.md).

Der Speicherort, Höhe und Breite des aktuellen Steuerelements werden in der unteren rechten Ecke der Statusleiste angezeigt. Wenn das gesamte Dialogfeld ausgewählt ist, zeigt die Statusleiste die Position im Dialogfeld als Ganzes, und seine Höhe und Breite.

## <a name="guides-and-grids"></a>Führungslinien und Raster

Sie können Anordnen von Steuerelementen in Dialogfeldern, mit der **Dialogfeld** -Editor in einer von drei verschiedenen Zuständen:

- Mit dem Führungslinien und Ränder auf (Standardeinstellung)

- Mit das Layoutraster für

- Ohne jegliche Features andocken oder Ausrichtung

Die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) enthält Schaltflächen, die den Status zu steuern. Um den Status zu ändern, wählen Sie das entsprechende Symbol. Sie können auch die Status ändern, mit der **Einstellungen für Führungslinien** Befehl die **Format** Menü.

Die **Einstellungen für Führungslinien** Dialogfeld hat die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**Layoutführungslinien**|Zeigt die Einstellungen für die Layoutführungslinien.|
|**Keine**|Blendet die Layout-Tools.|
|**Lineale und Führungslinien**|Wenn aktiviert, wird die Layouttools Lineale hinzugefügt; Führungslinien können in die Lineale platziert werden. Die Standard-Handbücher sind die Ränder, die durch Ziehen von verschoben werden können. Wählen Sie die Lineale, um eine Anleitung zu platzieren. Steuerelemente "Ausrichten" in den Anleitungen, wenn die Steuerelemente über oder neben dem Namen verschoben werden. Steuerelemente werden auch mit einer Anleitung verschieben, nachdem sie es angefügt wurden. Wenn ein Steuerelement in ein auf jeder Seite angefügt ist und eine Anleitung verschoben wird, ändert die Größe des Steuerelements.|
|**Raster**|Erstellt eine Layoutraster für Telefone. Neue Steuerelemente werden automatisch auf das Raster ausgerichtet.|
|**Rasterweite**|Zeigt die Einstellungen für den Rasterabstand in Box Dialogeinheiten (DLUs).|
|**Breite: DLUs**|Legt die Breite des Layoutrasters in DLUs fest. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier.|
|**Height: DLUs**|Legt die Höhe des Layoutrasters in DLUs fest. Eine vertikale DLU ist die durchschnittliche Höhe des geteilt durch acht Dialogfeld-Schriftart.|

### <a name="to-create-edit-and-delete-guides-and-margins"></a>Um zu erstellen, bearbeiten und Löschen von Führungslinien und Rändern

Ob verlagern Sie Steuerelemente, Hinzufügen von Steuerelementen, oder den aktuellen Layout neu anordnen, Anleitungen helfen ausrichten Sie Steuerelemente in einem Dialogfeld genau. Anleitungen, die als blaue gepunktete Linien angezeigt, über das Dialogfeld angezeigt, die im Editor, und entsprechende Pfeile in der Lineale am oberen und am linken Rand der **Dialogfeld** Editor.

Wenn Sie ein Dialogfeld erstellen, werden vier Ränder bereitgestellt. Ränder werden geänderte Anleitungen, die als blaue gepunktete Linien angezeigt werden. Finden Sie die folgenden Aktionen aus:

- Erstellen eine Führungslinie, dem Lineal, wählen Sie einmal um eine Anleitung zu erstellen. (Nur einem Klick erstellt ein neues Handbuch; Doppelklicken startet die **Einstellungen für Führungslinien** Dialogfeld, in dem Sie Einstellungen für Führungslinien angeben können.)

- Um eine Anleitung, in dem Dialogfeld festzulegen, wählen Sie im Handbuch, und ziehen Sie es in eine neue Position. (Sie können auch den Pfeil in der zugehörigen Handbuch ziehen das Lineal auswählen.) Die Koordinaten des Handbuchs werden in der Statusleiste am unteren Rand des Fensters und auf dem Lineal angezeigt. Zeigen Sie auf den Pfeil auf das Lineal, um die genaue Position des Handbuchs anzuzeigen.

- Um Ränder zu verschieben, ziehen Sie den Rand der neuen Position. Um einen Rand zu machen, verschieben Sie den Rand zu einer Position 0 (null). Klicken Sie zum Wiederherstellen des Rands, platzieren Sie den Mauszeiger über des Rands der Nullposition, und verschieben Sie den Rand in Position.

- Um eine Anleitung zu löschen, ziehen Sie die Anleitung aus das Dialogfeld, oder ziehen Sie den entsprechenden Pfeil vom Lineal.

### <a name="to-align-controls-on-a-guide"></a>Zum Ausrichten von Steuerelementen an einer Führungslinie

Die Ziehpunkte des Steuerelementen ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Anleitungen an Steuerelemente ausrichten, wenn keine zuvor im Handbuch angedockte Steuerelemente enthalten sind. Wenn eine Anleitung verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die an mehr als ein Handbuch Rasterlinie ausgerichtet werden geändert, wenn eine der Anleitungen verschoben wird.

Die Teilstriche in die Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU ist die durchschnittliche Höhe der Schriftart geteilt durch acht.

#### <a name="to-size-a-group-of-controls-with-guides"></a>Eine Gruppe von Steuerelementen mit Guides Größe

1. Richten Sie eine Seite des Steuerelements (oder Steuerelemente), um eine Anleitung.

1. Ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente).

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

1. Verschieben Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente).

#### <a name="to-change-the-intervals-of-the-tick-marks"></a>So ändern Sie die Intervalle der Teilstriche

Von der **Format** im Menü wählen **Einstellungen für Führungslinien**, klicken Sie dann in der **Rasterweite** an eine neue Breite und Höhe in DLUs.

### <a name="to-disable-guides"></a>So deaktivieren Sie Führungslinien

Sie können spezielle Schlüssel in Verbindung mit der Maus verwenden, so deaktivieren Sie die Andocken Auswirkungen der Anleitungen. Mithilfe der **Alt** Schlüssel deaktiviert die Andocken Auswirkungen des Handbuchs ausgewählt. Verschieben eine Anleitung mit den **UMSCHALT** Schlüssel wird verhindert, dass Steuerelemente automatisch auszurichten mit dem für das verschieben.

- Um die Andocken Auswirkungen der Anleitungen zu deaktivieren, ziehen Sie das Steuerelement bei gedrückter der **Alt** Schlüssel.

- Um Leitfäden ohne angedockte Steuerelemente verschoben zu verschieben, ziehen Sie die Führungslinie bei gedrückter der **UMSCHALT** Schlüssel.

- So deaktivieren Sie die Anleitungen, aus der **Format** Menü wählen **Einstellungen für Führungslinien**. Klicken Sie dann in der **Einstellungen für Führungslinien** Dialogfeld **Layoutführungslinien**Option **keine**.

   > [!NOTE]
   > Sie können auch den Zugriff auf die Lineal-Leiste doppelklicken dem **Einstellungen für Führungslinien** Dialogfeld.

> [!TIP]
> Eine Verknüpfung zum Deaktivieren von Führungslinien befindet sich auf die **Format** , wählen Sie im Menü **Führungslinien ein-/ausschalten**.

### <a name="to-modify-the-layout-grid"></a>Zum Ändern des Layoutrasters

Beim platzieren oder Anordnen von Steuerelementen in einem Dialogfeld, können Sie das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, scheinen die Steuerelemente ", die gepunkteten Zeilen im Raster ausrichten" einzurasten. Sie können Aktivieren dieses Feature "am Raster ausrichten" ein, und deaktivieren und Ändern der Größe der Rasterzellen des Layouts.

- Aktivieren das Layoutraster für Telefone oder zu deaktivieren, aus der **Format** Menü wählen **Einstellungen für Führungslinien**dann aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialogfeld** -Editor-Fenster mit den **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

- So ändern Sie die Größe des Layoutrasters aus der **Format** Menü wählen **Einstellungen für Führungslinien**, geben Sie dann die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4 DLUs.

## <a name="select-controls"></a>Auswählen von Steuerelementen

Auswählen von Steuerelementen auf Größe, ausrichten, verschieben, kopieren, oder löschen, und schließen Sie dann den gewünschten Vorgang. In den meisten Fällen müssen Sie zu verwenden, die Tools zur größenanpassung und die Ausrichtung auf mehrere Steuerelement auswählen, die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Wenn ein Steuerelement ausgewählt ist, einen schattierten Rahmen mit Solid (aktiv hat) oder leere (deaktivierte) "Ziehpunkten" kleine, die Quadrate in den Auswahlrahmen angezeigt werden. Wenn mehrere Steuerelemente ausgewählt sind, wird das dominante Steuerelement hat gefüllte Ziehpunkte, und alle anderen ausgewählten Steuerelemente haben leere Ziehpunkte.

Beim Ändern der Größe oder Ausrichtung mehrerer Steuerelemente, die **Dialogfeld** Editor verwendet, das "dominante Steuerelement" um zu bestimmen, wie die anderen Steuerelemente angepasst oder ausgerichtet sind. Standardmäßig ist das dominante Steuerelement das erste Steuerelement ausgewählt.

### <a name="to-select-controls"></a>Auswählen von Steuerelementen

1. In der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), wählen die **Zeiger** Tool.

1. Verwenden Sie die folgenden Schritte aus, um Ihre Auswahl zu treffen:

   - Ziehen Sie den Mauszeiger, um ein Auswahlfeld um Steuerelemente zu zeichnen, die Sie in einem Dialogfeld auswählen möchten. Wenn Sie die Maustaste loslassen, alle Steuerelemente innerhalb und sich überschneiden, werden das Auswahlfeld ausgewählt.

   - Halten Sie die **UMSCHALT** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

   - Halten Sie die **STRG** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

1. Zum Hinzufügen oder entfernen ein Steuerelement aus der Gruppe der ausgewählten Steuerelemente, halten Sie die **UMSCHALT** gedrückt, und wählen Sie das Steuerelement, das Sie hinzufügen oder entfernen möchten.

> [!NOTE]
> Gedrückt der **STRG** -Taste und der Auswahl eines Steuerelements in eine Auswahl treffen, die in die Auswahl des bestimmenden Steuerelements zu steuern.

### <a name="to-select-a-dominant-control"></a>Auswählen des bestimmenden Steuerelements

- Wenn das dominante Steuerelement angeben möchten, halten Sie die **STRG** gedrückt, und wählen Sie das Steuerelement, das Sie nutzen, um die Größe oder Position von anderen Steuerelementen beeinflussen möchten *erste*.

- Um das dominante Steuerelement zu ändern, deaktivieren Sie die aktuelle Auswahl dazu außerhalb aller derzeit ausgewählten Steuerelemente, und wiederholen Sie die vorherigen Schritte, und wählen ein anderes Steuerelement zuerst.

> [!NOTE]
> Die Ziehpunkte des bestimmenden Steuerelements sind solid, während die Ziehpunkte der untergeordneten Steuerelemente leer sind. Alle weiteren Ändern der Größe oder Ausrichtung basiert auf das dominante Steuerelement.

## <a name="size-controls"></a>Größe von Steuerelementen

Verwenden Sie die Ziehpunkte, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert es Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Aktive Ziehpunkte solid sind und wenn ein Ziehpunkt leerer ist, kann nicht das Steuerelement entlang dieser Achse geändert werden.

> [!TIP]
> Sie können auch die Größe eines Steuerelements ändern, durch das das Steuerelement an Führungslinien oder Rand andocken, oder durch das Verschieben einer Kontrolle und Anleitung von einem anderen angedockt.

### <a name="to-size-a-control"></a>Größe eines Steuerelements

1. Wählen Sie das Steuerelement.

1. Ziehen Sie die Ziehpunkte, um die Größe des Steuerelements zu ändern:

   - Ziehpunkte an den oberen und den Seiten die horizontale oder vertikale Größe geändert.

   - Ziehpunkte an den Ecken ändern Sie horizontale und vertikale Größe.

   > [!TIP]
   > Sie können die Steuerelement ein Dialog-Einheit (DLU) zu einem Zeitpunkt ändern, halten die **UMSCHALT** Schlüssel- und unter Verwendung der **rechts** und **unten** unten-Tasten.

> [!TIP]
> Öffnen Sie ein Steuerelement, um den Text angepasst automatisch die Größe der **Format** Menü oder klicken Sie auf das Steuerelement, und wählen **Größe an Inhalt anpassen**.

### <a name="to-make-controls-the-same-size"></a>Um die Steuerelemente die gleiche Größe fest.

Sie können eine Gruppe von Steuerelementen basierend auf der Größe des bestimmenden Steuerelements ändern.

1. Wählen Sie die Steuerelemente, die Sie die Größe ändern möchten.

   Das Steuerelement zuerst in der Reihe ausgewählt ist, das dominante Steuerelement. Die endgültige Größe der Steuerelemente in der Gruppe, hängt von der Größe des bestimmenden Steuerelements ab.

1. Von der **Format** Menü wählen **Größe angleichen**, wählen Sie dann entweder **sowohl**, **Höhe**, oder **Breite**.

### <a name="combo-box"></a>Kombinationsfeld

Sie können ein Kombinationsfeld Größe, wenn Sie sie zum Dialogfeld hinzufügen. Sie können auch die Größe des im Dropdown-Listenfeld angeben. Weitere Informationen finden Sie unter [Werte hinzufügen, um ein Kombinationsfeld-Steuerelement](../windows/adding-values-to-a-combo-box-control.md).

1. Wählen Sie die Dropdown-Pfeil-Schaltfläche rechts neben dem Kombinationsfeld aus.

   ![Pfeil in einem Kombinationsfeld in einem MFC-Projekt](../mfc/media/vccomboboxarrow.gif "VcComboBoxArrow")

   Die Gliederung des Steuerelements ändert die Größe des Kombinationsfelds mit den erweiterten Dropdown-Listenfeld-Bereich angezeigt.

1. Verwenden Sie den unteren Ziehpunkt, um die Anfangsgröße des Bereichs, Dropdown-Listenfeld ändern.

   ![Kombinationsfeld&#45;Box-Sizing in einem MFC-Projekt](../mfc/media/vccomboboxsizing.gif "VcComboBoxSizing")

1. Wählen Sie den Dropdown-Pfeil erneut aus, um der Teil der Dropdown-Listenfeld des Kombinationsfelds geschlossen.

### <a name="horizontal-scroll-bar"></a>Horizontalen Bildlaufleiste

Wenn Sie ein Listenfeld mit einer horizontalen Schiebeleiste eines Dialogfelds mithilfe von MFC-Klassen hinzufügen, wird nicht die Bildlaufleiste automatisch in Ihrer Anwendung angezeigt.

Legen Sie eine maximale Breite für das breiteste Element durch Aufrufen von [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) in Ihrem Code. Ohne diesen Wert wird nicht die Bildlaufleiste angezeigt, auch wenn die Elemente im Listenfeld breiter als das Feld sind.

## <a name="align-controls"></a>Ausrichten von Steuerelementen

1. Wählen Sie die Steuerelemente, die Sie ausrichten möchten. Achten Sie darauf, um das Steuerelement auszuwählen, die vorherrschende werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen von die Ausrichtung, oder Ändern der Größe Befehl sein.

   Die letzte Position in der Gruppe von Steuerelementen, hängt von der Position des bestimmenden Steuerelements ab.

1. Von der **Format** Menü wählen **ausrichten**, und wählen Sie dann eines der folgenden Ausrichtungen:

   |Ausrichtung|Beschreibung|
   |-----|-----------|
   |`Lefts`|Richtet den ausgewählten Steuerelemente linksbündig.|
   |`Centers`|Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt.|
   |`Rights`|Richtet den ausgewählten Steuerelemente entlang der rechten Seite liegen.|
   |`Tops`|Richtet die ausgewählten Steuerelemente an die oberen Ränder.|
   |`Middles`|Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt.|
   |`Bottoms`|Richtet den ausgewählten Steuerelemente an die unteren Rändern.|

### <a name="to-even-spacing-between-controls"></a>Auch der Abstand zwischen Steuerelementen

Die **Dialogfeld** -Editor können Sie an Steuerelemente der Platz gleichmäßig auf die äußersten Steuerelemente ausgewählt.

1. Wählen Sie die Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **gleichmäßig**, und wählen Sie dann eine der folgenden Ausrichtungsbefehle:

   |Abstand|Beschreibung|
   |---|---|
   |`Across`|Speicherplatz Steuerelemente gleichmäßig zwischen dem äußeren linken und dem äußersten rechten ausgewählten Steuerelement.|
   |`Down`|Speicherplatz Steuerelemente gleichmäßig zwischen dem obersten und untersten Steuerelements ausgewählt.|

### <a name="to-center-controls"></a>Zentrieren von Steuerelementen

1. Wählen Sie das Steuerelement oder Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **Center im Dialogfeld**, und wählen Sie dann eine der folgenden Aktionen:

   |Anordnung|Beschreibung|
   |---|---|
   |`Vertical`|Zentrieren Sie Steuerelemente in das Dialogfeld vertikal.|
   |`Horizontal`|Zentrieren von Steuerelementen im Dialogfeld horizontal.|

### <a name="to-arrange-push-buttons"></a>Anordnen von Schaltflächen

1. Wählen Sie eine oder mehrere Schaltflächen an.

1. Von der **Format** Menü wählen **Schaltflächen anordnen**, und wählen Sie dann eine der folgenden Aktionen:

   |Anordnung|Beschreibung|
   |---|---|
   |`Right`|Richtet die Schaltflächen am rechten Rand des Dialogfelds.|
   |`Bottom`|Richtet die Schaltflächen am unteren Rand des Dialogfelds.|

   Wenn Sie ein Steuerelement als eine Schaltfläche auswählen, wird nicht seine Position beeinflusst.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)