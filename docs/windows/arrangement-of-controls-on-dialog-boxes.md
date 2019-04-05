---
title: 'Vorgehensweise: Formularlayout-Steuerelemente (C++) | Microsoft-Dokumentation'
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
ms.openlocfilehash: 878b7371dfa77880d68f1001444ed44b84d7240c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037420"
---
# <a name="how-to-layout-controls-c"></a>Vorgehensweise: Formularlayout-Steuerelemente (C++)

Die **Dialog-Editor** Layouttools, ausrichten und Größe von Steuerelementen automatisch, bietet. Für die meisten Aufgaben können Sie die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Alle **Dialog-Editor** Symbolleistenbefehle stehen auch in der **Format** haben Sie im Menü, und die meisten [Tastenkombinationen](../windows/accelerator-keys-for-the-dialog-editor.md).

Viele Layoutbefehle für Dialogfelder sind verfügbar, nur, wenn mehr als ein Steuerelement ausgewählt ist. Sie können eine einzelne oder mehrere Steuerelemente auswählen, und wenn mehr als ein Steuerelement ausgewählt ist, das erste Objekt, das Sie auswählen, wird standardmäßig das dominante Steuerelement.

Der Speicherort, Höhe und Breite des aktuellen Steuerelements werden in der unteren rechten Ecke der Statusleiste angezeigt. Wenn das gesamte Dialogfeld ausgewählt ist, zeigt die Statusleiste die Position im Dialogfeld als Ganzes, und seine Höhe und Breite.

## <a name="arrange-controls"></a>Anordnen von Steuerelementen

Sie können Anordnen von Steuerelementen in Dialogfeldern, mit der **Dialog-Editor** in einem von drei verschiedenen Zuständen:

- Führungslinien und Ränder auf Wenn Sie als Standard festlegen.

- Mit das Layoutraster für.

- Ohne jegliche Snap- oder Ausrichtung-Features.

Die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) enthält Schaltflächen, die den Status zu steuern.

- Um den Status zu ändern, wählen Sie das entsprechende Symbol, oder wechseln Sie zum Menü **Format** > **Einstellungen für Führungslinien**.

Die **Einstellungen für Führungslinien** Dialogfeld hat die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**Layoutführungslinien**|Zeigt die Einstellungen für die Layoutführungslinien.|
|**Keiner**|Blendet die Layout-Tools.|
|**Lineale und Führungslinien**|Wenn aktiviert, wird die Layouttools Lineale hinzugefügt und Anleitungen erfahren, wie in der Lineale platziert werden können. Die Standard-Handbücher sind die Ränder.|
|**Raster**|Erstellt eine Layoutraster für Telefone. Neue Steuerelemente werden automatisch auf das Raster ausgerichtet.|
|**Rasterweite**|Zeigt die Einstellungen für den Rasterabstand in Box Dialogeinheiten (DLUs).|
|**Breite: DLUs**|Legt die Breite des Layoutrasters in DLUs fest. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch 4.|
|**Höhe: DLUs**|Legt die Höhe des Layoutrasters in DLUs fest. Eine vertikale DLU entspricht der durchschnittlichen Höhe der Dialogfeld-Schriftart dividiert durch 8.|

### <a name="guides-and-margins"></a>Führungslinien und Rändern

Ob verlagern Sie Steuerelemente, Hinzufügen von Steuerelementen, oder den aktuellen Layout neu anordnen, Führungslinien und Rändern helfen ausrichten Sie Steuerelemente in einem Dialogfeld genau.

Wenn Sie ein Dialogfeld erstellen, vier geänderte Anleitungen, die Ränder aufgerufen werden bereitgestellt und werden als blaue gepunktete Linien angezeigt.

- Um Ränder zu verschieben, ziehen Sie den Rand der neuen Position.

- Um einen Rand zu machen, verschieben Sie den Rand zu einer Position 0 (null).

- Klicken Sie zum Wiederherstellen des Rands, platzieren Sie den Mauszeiger über des Rands der Nullposition, und verschieben Sie den Rand in Position.

Anleitungen, die als blaue gepunktete Linien angezeigt, über das Dialogfeld angezeigt, die im Editor, und entsprechende Pfeile in der Lineale am oberen und am linken Rand der **Dialog-Editor**. Die Ziehpunkte des Steuerelementen ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Anleitungen an Steuerelemente ausrichten, wenn keine zuvor im Handbuch angedockte Steuerelemente enthalten sind. Wenn eine Anleitung verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die an mehr als ein Handbuch Rasterlinie ausgerichtet werden geändert, wenn eine der Anleitungen verschoben wird.

- So erstellen eine Anleitung, in dem Lineal, einmal auswählen, um eine Anleitung zu erstellen oder doppelklicken Sie auf, um zu starten der **Einstellungen für Führungslinien** Dialogfeld, in dem Sie Einstellungen für Führungslinien angeben können.

- Um eine Anleitung für das Dialogfeld zu festzulegen, wählen Sie das Handbuch und ziehen Sie es in eine neue Position, oder wählen Sie den Pfeil in das Lineal, im zugehörige Handbuch zu ziehen.

   Die Koordinaten des Handbuchs werden angezeigt, in der Statusleiste am unteren Rand des Fensters und auf dem Lineal oder den Mauszeiger über den Pfeil auf das Lineal, um die genaue Position des Handbuchs anzuzeigen.

- Um eine Anleitung zu löschen, ziehen Sie die Anleitung aus das Dialogfeld, oder ziehen Sie den entsprechenden Pfeil vom Lineal.

Die Teilstriche in die Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU ist die durchschnittliche Höhe der Schriftart dividiert durch 8.

- Um die Intervalle der Teilstriche zu ändern, wechseln Sie zum Menü **Format** > **Einstellungen für Führungslinien**, klicken Sie dann in der **Rasterweite** an eine neue Breite und Höhe in DLUs.

### <a name="layout-grid"></a>Layoutraster

Wenn Sie platziert sind, oder Anordnen von Steuerelementen in einem Dialogfeld aus, das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, werden Steuerelemente die gepunkteten Zeilen des Rasters ausgerichtet einzurasten.

- Um das Layoutraster aktivieren / deaktivieren, wechseln Sie zum Menü **Format** > **Einstellungen für Führungslinien** und aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialog-Editor** Windows mithilfe der **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

- Gehen Sie zum Ändern der Größe des Layoutrasters zum Menü **Format** > **Einstellungen für Führungslinien** , und geben Sie die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4.

### <a name="disable-guides"></a>Deaktivieren von Führungslinien

Sie können spezielle Schlüssel in Verbindung mit der Maus verwenden, so deaktivieren Sie die Andocken Auswirkungen der Anleitungen. Mithilfe der **Alt** Schlüssel deaktiviert die Andocken Auswirkungen des Handbuchs ausgewählt. Verschieben eine Anleitung mit den **UMSCHALT** Schlüssel wird verhindert, dass Steuerelemente automatisch auszurichten mit dem für das verschieben.

- Um die Andocken Auswirkungen der Anleitungen zu deaktivieren, ziehen Sie das Steuerelement bei gedrückter der **Alt** Schlüssel.

- Um Leitfäden ohne angedockte Steuerelemente verschoben zu verschieben, ziehen Sie die Führungslinie bei gedrückter der **UMSCHALT** Schlüssel.

- Um die Handbücher zu deaktivieren, wechseln Sie zum Menü **Format** > **Einstellungen für Führungslinien**. Klicken Sie unter **Layoutführungslinien**Option **keine**.

   > [!TIP]
   > Sie können auch die Verknüpfung im Menü **Format** > **Führungslinien ein-/ausschalten**.

## <a name="select-controls"></a>Auswählen von Steuerelementen

Auswählen von Steuerelementen auf Größe, ausrichten, verschieben, kopieren, oder löschen, und schließen Sie dann den gewünschten Vorgang. In den meisten Fällen müssen Sie zu verwenden, die Tools zur größenanpassung und die Ausrichtung auf mehrere Steuerelement auswählen, die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Wenn ein Steuerelement ausgewählt ist, hat es einen schattierten Rahmen mit Solid (aktiv) oder leere (deaktivierte) Ziehpunkten, kleine Quadrate, die in den Auswahlrahmen angezeigt werden. Wenn mehrere Steuerelemente ausgewählt sind, wird das dominante Steuerelement hat gefüllte Ziehpunkte, und alle anderen ausgewählten Steuerelemente haben leere Ziehpunkte.

- Um Steuerelemente, wählen Sie die [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), wählen die **Zeiger** Konfigurationstool, und gehen Sie die folgenden Schritte aus, um Ihre Auswahl zu treffen:

  - Ziehen Sie den Mauszeiger, um ein Auswahlfeld um Steuerelemente zu zeichnen, die Sie in einem Dialogfeld auswählen möchten. Wenn Sie die Maustaste loslassen, alle Steuerelemente innerhalb und sich überschneiden, werden das Auswahlfeld ausgewählt.

  - Halten Sie die **UMSCHALT** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

  - Halten Sie die **STRG** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

- Zum Hinzufügen oder entfernen ein Steuerelement aus der Gruppe der ausgewählten Steuerelemente, halten Sie die **UMSCHALT** gedrückt, und wählen Sie das Steuerelement, das Sie hinzufügen oder entfernen möchten.

### <a name="dominant-controls"></a>Bestimmende Steuerelemente

Beim Ändern der Größe oder Ausrichtung mehrerer Steuerelemente, die **Dialog-Editor** des bestimmenden Steuerelements verwendet, um zu bestimmen, wie die anderen Steuerelemente angepasst oder ausgerichtet sind. Standardmäßig ist das dominante Steuerelement das erste Steuerelement ausgewählt.

- Wenn das dominante Steuerelement angeben möchten, halten Sie die **STRG** gedrückt, und wählen Sie das Steuerelement, das Sie nutzen, um die Größe oder Position von anderen Steuerelementen beeinflussen möchten *erste*. Gedrückt der **STRG** -Taste und der Auswahl eines Steuerelements in einer Auswahl werden auch vornehmen, die in die Auswahl des bestimmenden Steuerelements zu steuern.

- Klicken Sie zum Ändern des bestimmenden Steuerelements deaktivieren Sie die aktuelle Auswahl dazu außerhalb aller derzeit ausgewählten Steuerelemente, und wiederholen Sie die oben genannten Schritte, und wählen ein anderes Steuerelement *erste*.

> [!NOTE]
> Die Ziehpunkte des bestimmenden Steuerelements sind solid, während die Ziehpunkte der untergeordneten Steuerelemente leer sind. Alle weiteren Ändern der Größe oder Ausrichtung basiert auf das dominante Steuerelement.

## <a name="size-controls"></a>Größe von Steuerelementen

Verwenden Sie die Ziehpunkte, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert es Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Aktive Ziehpunkte solid sind und wenn ein Ziehpunkt leerer ist, kann nicht das Steuerelement entlang dieser Achse geändert werden.

- Um die Größe eines Steuerelements zu ändern, wählen Sie das Steuerelement, und ziehen Sie die Ziehpunkte, um die Größe ändern.

  - Ziehpunkte an den oberen und den Seiten die horizontale oder vertikale Größe geändert.

  - Ziehpunkte an den Ecken ändern Sie horizontale und vertikale Größe.

   > [!TIP]
   > Sie können die Steuerelement ein Dialog-Einheit (DLU) zu einem Zeitpunkt ändern, halten die **UMSCHALT** Schlüssel- und unter Verwendung der **rechts** und **unten** unten-Tasten.

- Um ein Steuerelement, um den Text angepasst automatisch skalieren zu können, wechseln Sie zum Menü **Format** oder klicken Sie auf das Steuerelement, und wählen **Größe an Inhalt anpassen**.

- Um Steuerelemente auf die gleiche Größe machen, wählen Sie die Steuerelemente, die Sie verwenden möchten, verwenden Sie die Größe, und wechseln Sie zum Menü **Format** > **Größe angleichen**, wählen Sie dann entweder **sowohl**, **Höhe**, oder **Breite**.

   Sie ändern eine Gruppe von Steuerelementen basierend auf der Größe des bestimmenden Steuerelements, das das Steuerelement zuerst in der Reihe ausgewählt ist. Die endgültige Größe der Steuerelemente in der Gruppe, hängt von der Größe des bestimmenden Steuerelements ab.

- Um eine Gruppe von Steuerelementen mit Anleitungen zu Größe, richten Sie eine Seite des Steuerelements (oder Steuerelemente) in ein, und ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente). Jetzt können Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente) verschieben.

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

### <a name="other-controls"></a>Andere Steuerelemente

Sie können ein Kombinationsfeld Größe, wenn Sie sie zum Dialogfeld hinzufügen. Sie können auch die Größe des im Dropdown-Listenfeld angeben. Weitere Informationen finden Sie unter [Werte hinzufügen, um ein Kombinationsfeld-Steuerelement](../windows/adding-values-to-a-combo-box-control.md).

1. Wählen Sie die Dropdown-Pfeil-Schaltfläche rechts neben dem Kombinationsfeld aus.

   ![Pfeil in einem Kombinationsfeld in einem MFC-Projekt](../mfc/media/vccomboboxarrow.gif "VcComboBoxArrow")

   Die Gliederung des Steuerelements ändert die Größe des Kombinationsfelds mit den erweiterten Dropdown-Listenfeld-Bereich angezeigt.

1. Verwenden Sie den unteren Ziehpunkt, um die Anfangsgröße des Bereichs, Dropdown-Listenfeld ändern.

   ![Kombinationsfeld&#45;Box-Sizing in einem MFC-Projekt](../mfc/media/vccomboboxsizing.gif "VcComboBoxSizing")

1. Wählen Sie den Dropdown-Pfeil erneut aus, um der Teil der Dropdown-Listenfeld des Kombinationsfelds geschlossen.

> [!NOTE]
> Wenn Sie ein Listenfeld mit einer horizontalen Schiebeleiste in einem Dialogfeld unter Verwendung von MFC hinzufügen, wird nicht die Bildlaufleiste automatisch in Ihrer Anwendung angezeigt.
>
> Legen Sie eine maximale Breite für das breiteste Element durch Aufrufen von [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) in Ihrem Code. Ohne diesen Wert wird nicht die Bildlaufleiste angezeigt, auch wenn die Elemente im Listenfeld breiter als das Feld sind.

## <a name="align-controls"></a>Ausrichten von Steuerelementen

- Wählen Sie zum Ausrichten von Steuerelementen, die Steuerelemente, die Sie ausrichten möchten. Wechseln Sie zum Menü **Format** > **ausrichten** , und wählen Sie eines der folgenden Ausrichtungen:

   |Ausrichtung|Beschreibung|
   |-----|-----------|
   |**Links ausrichten**|Richtet den ausgewählten Steuerelemente linksbündig.|
   |**Rechenzentren**|Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt.|
   |**Rechte**|Richtet den ausgewählten Steuerelemente entlang der rechten Seite liegen.|
   |**Nach oben**|Richtet die ausgewählten Steuerelemente an die oberen Ränder.|
   |**Mittig**|Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt.|
   |**Unten ausrichten**|Richtet den ausgewählten Steuerelemente an die unteren Rändern.|

   Achten Sie darauf, um das Steuerelement auszuwählen, die vorherrschende werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen die Ausrichtung oder größenanpassung Befehl aus, wie die Position des bestimmenden Steuerelements die letzte Position der Gruppe von Steuerelementen abhängig sein.

- Wählen Sie für gleichmäßig Speicherplatz-Steuerelemente die Steuerelemente, die Sie neu anordnen möchten. Wechseln Sie zum Menü **Format** > **gleichmäßig** , und wählen Sie eine der folgenden Ausrichtungsbefehle:

   |Abstand|Beschreibung|
   |---|---|
   |**Über**|Speicherplatz Steuerelemente gleichmäßig zwischen dem äußeren linken und dem äußersten rechten ausgewählten Steuerelement.|
   |**Nach unten**|Speicherplatz Steuerelemente gleichmäßig zwischen dem obersten und untersten Steuerelements ausgewählt.|

- Um Steuerelemente zu zentrieren, wählen Sie das Steuerelement oder Steuerelemente, die Sie neu anordnen möchten. Wechseln Sie zum Menü **Format** > **Center im Dialogfeld** und wählen Sie eine der folgenden Aktionen:

   |Anordnung|Beschreibung|
   |---|---|
   |**Vertikal**|Zentrieren Sie Steuerelemente in das Dialogfeld vertikal.|
   |**Horizontal**|Zentrieren von Steuerelementen im Dialogfeld horizontal.|

- Wählen Sie eine oder mehrere Schaltflächen zum Ausrichten von Schaltflächen. Wechseln Sie zum Menü **Format** > **Schaltflächen anordnen**, wählen Sie dann eine der folgenden Aktionen:

   |Anordnung|Beschreibung|
   |---|---|
   |**Rechts**|Richtet die Schaltflächen am rechten Rand des Dialogfelds.|
   |**Bottom**|Richtet die Schaltflächen am unteren Rand des Dialogfelds.|

   Wenn Sie ein Steuerelement als eine Schaltfläche auswählen, wird nicht seine Position beeinflusst.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Verwalten von Dialogfeld-Steuerelemente](controls-in-dialog-boxes.md)<br/>
[Vorgehensweise: Hinzufügen, bearbeiten oder Löschen von Steuerelementen](adding-editing-or-deleting-controls.md)<br/>
[Vorgehensweise: Steuern des Zugriffs und Werte definieren](defining-mnemonics-access-keys.md)<br/>