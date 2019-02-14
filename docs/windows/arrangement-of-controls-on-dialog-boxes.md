---
title: Anordnung von Steuerelementen in Dialogfeldern (C++) | Microsoft-Dokumentation
ms.date: 11/04/2016
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
ms.openlocfilehash: 99667898428fe9532d59277bfedafd24927304dc
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264880"
---
# <a name="arrangement-of-controls-on-dialog-boxes-c"></a>Anordnung von Steuerelementen in Dialogfeldern (C++)

Die **Dialogfeld** -Editor bietet Layouttools, ausrichten und Größe von Steuerelementen automatisch. Für die meisten Aufgaben können Sie die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Alle **Dialog-Editor** Symbolleistenbefehle stehen auch in der **Format** haben Sie im Menü, und die meisten [Tastenkombinationen](../windows/accelerator-keys-for-the-dialog-editor.md).

Viele Layoutbefehle für Dialogfelder sind verfügbar, nur, wenn mehr als ein Steuerelement ausgewählt ist. Sie können eine einzelne oder mehrere Steuerelemente auswählen, und wenn mehr als ein Steuerelement ausgewählt ist, das erste Objekt, das Sie auswählen, wird standardmäßig "dominanten" Steuerelements. Informationen zum Auswählen von Steuerelementen und das dominante Steuerelement, finden Sie unter [Markieren von Steuerelementen](../windows/selecting-controls.md).

Der Speicherort, Höhe und Breite des aktuellen Steuerelements werden in der unteren rechten Ecke der Statusleiste angezeigt. Wenn das gesamte Dialogfeld ausgewählt ist, zeigt die Statusleiste die Position im Dialogfeld als Ganzes, und seine Höhe und Breite.

## <a name="dialog-editor-states-guides-and-grids"></a>Gibt an Dialog-Editors (Führungslinien und Raster)

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

### <a name="create-and-set-guides-and-margins"></a>Erstellen und Festlegen von Führungslinien und Rändern

Ob verlagern Sie Steuerelemente, Hinzufügen von Steuerelementen, oder den aktuellen Layout neu anordnen, Anleitungen helfen ausrichten Sie Steuerelemente in einem Dialogfeld genau. Anleitungen, die als blaue gepunktete Linien angezeigt, über das Dialogfeld angezeigt, die im Editor, und entsprechende Pfeile in der Lineale am oberen und am linken Rand der **Dialogfeld** Editor.

Wenn Sie ein Dialogfeld erstellen, werden vier Ränder bereitgestellt. Ränder werden geänderte Anleitungen, die als blaue gepunktete Linien angezeigt werden.

|Prozess|Schritte|
|----------------|----------------|
|Um eine Anleitung zu erstellen.|Dem Lineal wählen Sie einmal, um eine Anleitung zu erstellen. (Nur einem Klick erstellt ein neues Handbuch; Doppelklicken startet die **Einstellungen für Führungslinien** Dialogfeld, in dem Sie Einstellungen für Führungslinien angeben können.)|
|Eine Führungslinie festlegen|Klicken Sie auf das Dialogfeld klicken Sie auf der Anleitung, und ziehen Sie es an eine neue Position. (Sie können auch den Pfeil in der zugehörigen Handbuch ziehen das Lineal klicken.)<br/><br/>Die Koordinaten des Handbuchs werden in der Statusleiste am unteren Rand des Fensters und auf dem Lineal angezeigt. Zeigen Sie auf den Pfeil auf das Lineal, um die genaue Position des Handbuchs anzuzeigen.|
|So löschen Sie eine Führungslinie|Ziehen Sie das Handbuch aus das Dialogfeld ein.<br/><br/>\- oder –<br/><br/>Ziehen Sie die entsprechenden Pfeil vom Lineal.|
|So verschieben Sie Ränder|Ziehen Sie den Rand auf die neue Position ein.<br/><br/>Um einen Rand zu machen, verschieben Sie den Rand zu einer Position 0 (null). Klicken Sie zum Wiederherstellen des Rands, platzieren Sie den Mauszeiger über des Rands der Nullposition, und verschieben Sie den Rand in Position.|

### <a name="align-controls-on-a-guide"></a>Ausrichten von Steuerelementen an einer Führungslinie

Die Ziehpunkte des Steuerelementen ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Anleitungen an Steuerelemente ausrichten, wenn keine zuvor im Handbuch angedockte Steuerelemente enthalten sind. Wenn eine Anleitung verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die an mehr als ein Handbuch Rasterlinie ausgerichtet werden geändert, wenn eine der Anleitungen verschoben wird.

Die Teilstriche in die Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU ist die durchschnittliche Höhe der Schriftart geteilt durch acht.

Eine Gruppe von Steuerelementen mit Guides Größe:

1. Richten Sie eine Seite des Steuerelements (oder Steuerelemente), um eine Anleitung.

1. Ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente).

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

1. Verschieben Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente).

Die Intervalle der Teilstriche zu ändern:

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld die **Rasterweite** an eine neue Breite und Höhe in DLUs.

### <a name="disable-guides"></a>Deaktivieren von Führungslinien

Sie können spezielle Schlüssel in Verbindung mit der Maus verwenden, so deaktivieren Sie die Andocken Auswirkungen der Anleitungen. Mithilfe der **Alt** Schlüssel deaktiviert die Andocken Auswirkungen des Handbuchs ausgewählt. Verschieben eine Anleitung mit den **UMSCHALT** Schlüssel wird verhindert, dass Steuerelemente automatisch auszurichten mit dem für das verschieben.

- Um die Andocken Auswirkungen der Anleitungen zu deaktivieren, ziehen Sie das Steuerelement bei gedrückter der **Alt** Schlüssel.

- Um Leitfäden ohne angedockte Steuerelemente verschoben zu verschieben, ziehen Sie die Führungslinie bei gedrückter der **UMSCHALT** Schlüssel.

- So deaktivieren Sie die Anleitungen, aus der **Format** Menü wählen **Einstellungen für Führungslinien**. Klicken Sie dann in der **Einstellungen für Führungslinien** Dialogfeld **Layoutführungslinien**Option **keine**.

   > [!NOTE]
   > Sie können auch den Zugriff auf die Lineal-Leiste doppelklicken dem **Einstellungen für Führungslinien** Dialogfeld.

> [!TIP]
> Eine Verknüpfung zum Deaktivieren von Führungslinien befindet sich auf die **Format** , wählen Sie im Menü **Führungslinien ein-/ausschalten**.

### <a name="modify-the-layout-grid"></a>Ändern des Layoutrasters

Beim platzieren oder Anordnen von Steuerelementen in einem Dialogfeld, können Sie das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, scheinen die Steuerelemente ", die gepunkteten Zeilen im Raster ausrichten" einzurasten. Sie können Aktivieren dieses Feature "am Raster ausrichten" ein, und deaktivieren und Ändern der Größe der Rasterzellen des Layouts.

Um das Layoutraster aktivieren / deaktivieren:

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialogfeld** -Editor-Fenster mit den **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

So ändern Sie die Größe des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld geben die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4 DLUs.

## <a name="selecting-controls"></a>Markieren von Steuerelementen

Auswählen von Steuerelementen auf Größe, ausrichten, verschieben, kopieren, oder löschen, und schließen Sie dann den gewünschten Vorgang. In den meisten Fällen müssen Sie zu verwenden, die Tools zur größenanpassung und die Ausrichtung auf mehrere Steuerelement auswählen, die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Wenn ein Steuerelement ausgewählt ist, einen schattierten Rahmen mit Solid (aktiv hat) oder leere (deaktivierte) "Ziehpunkten" kleine, die Quadrate in den Auswahlrahmen angezeigt werden. Wenn mehrere Steuerelemente ausgewählt sind, wird das dominante Steuerelement hat gefüllte Ziehpunkte, und alle anderen ausgewählten Steuerelemente haben leere Ziehpunkte.

Beim Ändern der Größe oder Ausrichtung mehrerer Steuerelemente, die **Dialogfeld** Editor verwendet, das "dominante Steuerelement" um zu bestimmen, wie die anderen Steuerelemente angepasst oder ausgerichtet sind. Standardmäßig ist das dominante Steuerelement das erste Steuerelement ausgewählt.

### <a name="to-select-multiple-controls"></a>Zum Auswählen mehrerer Steuerelemente

1. In der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), wählen die **Zeiger** Tool.

1. Verwenden Sie die folgenden Schritte aus, um Ihre Auswahl zu treffen:

   - Ziehen Sie den Mauszeiger, um ein Auswahlfeld um Steuerelemente zu zeichnen, die Sie in einem Dialogfeld auswählen möchten. Wenn Sie die Maustaste loslassen, alle Steuerelemente innerhalb und sich überschneiden, werden das Auswahlfeld ausgewählt.

   - Halten Sie die **UMSCHALT** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

   - Halten Sie die **STRG** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

### <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Ein Steuerelement aus einer Gruppe von ausgewählten Steuerelemente zu entfernen oder Hinzufügen des Steuerelements auf eine Gruppe von ausgewählten Steuerelemente

Mit der eine Gruppe von Steuerelementen, die ausgewählt werden soll, halten Sie die **UMSCHALT** gedrückt, und wählen Sie das Steuerelement, das Sie verwenden möchten, um die vorhandene Auswahl hinzufügen oder daraus entfernen.

   > [!NOTE]
   > Gedrückt der **STRG** -Taste und der Auswahl eines Steuerelements in eine Auswahl treffen, die in die Auswahl des bestimmenden Steuerelements zu steuern.

### <a name="to-specify-the-dominant-control"></a>Zum Angeben des bestimmenden Steuerelements

Halten Sie die **STRG** gedrückt, und wählen Sie das Steuerelement, das Sie nutzen, um die Größe oder Position von anderen Steuerelementen beeinflussen möchten *erste*.

> [!NOTE]
> Die Ziehpunkte des bestimmenden Steuerelements sind solid, während die Ziehpunkte der untergeordneten Steuerelemente leer sind. Alle weiteren Ändern der Größe oder Ausrichtung basiert auf das dominante Steuerelement.

### <a name="to-change-the-dominant-control"></a>Ändern des bestimmenden Steuerelements

1. Löschen Sie die aktuelle Auswahl, indem Sie die außerhalb aller derzeit ausgewählten Steuerelemente auf.

1. Wiederholen Sie die vorherigen Schritte, und wählen ein anderes Steuerelement zuerst aus.

## <a name="sizing-controls"></a>Anpassen von Steuerelementen

Verwenden Sie die Ziehpunkte, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert es Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Es sind aktive Ziehpunkte gefüllt. Wenn ein Ziehpunkt leerer ist, kann nicht das Steuerelement entlang dieser Achse Größe geändert werden.

Sie können auch die Größe eines Steuerelements ändern, durch das das Steuerelement an Führungslinien oder Rand andocken, oder durch das Verschieben einer Kontrolle und Anleitung von einem anderen angedockt.

### <a name="to-size-an-individual-control"></a>Ein einzelnes Steuerelement seine Größe festlegen

1. Wählen Sie das Steuerelement.

1. Ziehen Sie die Ziehpunkte, um die Größe des Steuerelements zu ändern:

   - Ziehpunkte an den oberen und den Seiten die horizontale oder vertikale Größe geändert.

   - Ziehpunkte an den Ecken ändern Sie horizontale und vertikale Größe.

   > [!TIP]
   > Sie können die Steuerelement ein Dialog-Einheit (DLU) zu einem Zeitpunkt ändern, halten die **UMSCHALT** Schlüssel- und unter Verwendung der **Pfeil nach rechts** und **nach-unten-** Schlüssel.

### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Automatisch die Größe ein Steuerelement für den Text angepasst

Wählen Sie **Größe an Inhalt anpassen** aus der **Format** Menü oder klicken Sie auf das Steuerelement, und wählen Sie **Größe an Inhalt anpassen** aus dem Kontextmenü.

### <a name="to-make-controls-the-same-width-height-or-size"></a>Um machen steuert die gleiche Breite, Höhe oder Größe

Sie können eine Gruppe von Steuerelementen basierend auf der Größe des bestimmenden Steuerelements ändern.

1. Wählen Sie die Steuerelemente, die Sie die Größe ändern möchten.

   Das Steuerelement zuerst in der Reihe ausgewählt ist, das dominante Steuerelement. Die endgültige Größe der Steuerelemente in der Gruppe, hängt von der Größe des bestimmenden Steuerelements ab.

1. Von der **Format** Menü wählen **Größe angleichen**, wählen Sie dann **sowohl**, **Höhe**, oder **Breite**.

### <a name="to-set-the-size-of-the-combo-box-and-its-drop-down-list"></a>Die Größe des Kombinationsfeld Feld und der Dropdown-Liste festgelegt

Sie können ein Kombinationsfeld Größe, wenn Sie sie zum Dialogfeld hinzufügen. Sie können auch die Größe des im Dropdown-Listenfeld angeben. Weitere Informationen finden Sie unter [Werte hinzufügen, um ein Kombinationsfeld-Steuerelement](../windows/adding-values-to-a-combo-box-control.md).

#### <a name="to-size-a-combo-box"></a>Die Größe eines Kombinationsfelds

1. Wählen Sie das Kombinationsfeld-Steuerelement in einem Dialogfeld an.

   Anfangs sind nur die Rechte und linke Ziehpunkt aktiv.

1. Verwenden Sie die Ziehpunkte, um die Breite des Kombinationsfelds festzulegen.

Sie können auch die vertikale Größe des der Dropdownteil des Kombinationsfelds festlegen.

#### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Zum Festlegen von der Größe des Kombinationsfeld-Dropdown-Liste

1. Wählen Sie die Dropdown-Pfeil-Schaltfläche rechts neben dem Kombinationsfeld aus.

   ![Pfeil in einem Kombinationsfeld in einem MFC-Projekt](../mfc/media/vccomboboxarrow.gif "VcComboBoxArrow")

   Die Gliederung des Steuerelements ändert die Größe des Kombinationsfelds mit den erweiterten Dropdown-Listenfeld-Bereich angezeigt.

1. Verwenden Sie den unteren Ziehpunkt, um die Anfangsgröße des Bereichs, Dropdown-Listenfeld ändern.

   ![Kombinationsfeld&#45;Box-Sizing in einem MFC-Projekt](../mfc/media/vccomboboxsizing.gif "VcComboBoxSizing")

1. Wählen Sie den Dropdown-Pfeil erneut aus, um der Teil der Dropdown-Listenfeld des Kombinationsfelds geschlossen.

### <a name="to-set-the-width-of-a-horizontal-scroll-bar-and-make-it-appear"></a>Legen Sie die Breite einer horizontalen Schiebeleiste, und stellen es so aussieht

Wenn Sie ein Listenfeld mit einer horizontalen Schiebeleiste eines Dialogfelds mithilfe von MFC-Klassen hinzufügen, wird nicht die Bildlaufleiste automatisch in Ihrer Anwendung angezeigt.

Legen Sie eine maximale Breite für das breiteste Element durch Aufrufen von [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) in Ihrem Code.

   Ohne diesen Wert wird nicht die Bildlaufleiste angezeigt, auch wenn die Elemente im Listenfeld breiter als das Feld sind.

## <a name="group-radio-buttons-on-a-dialog-box"></a>Gruppe von Optionsfeldern in einem Dialogfeld

Wenn Sie ein Dialogfeld Optionsschaltflächen hinzufügen, behandeln sie als Gruppe durch Festlegen einer **Gruppe** -Eigenschaft in der **Eigenschaften** Fenster für die erste Schaltfläche in der Gruppe. Eine Steuerelement-ID für das betreffende Optionsfeld wird dann im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)angezeigt und ermöglicht das Hinzufügen einer Membervariablen zur Gruppe der Optionsfelder.

Ein Dialogfeld kann mehrere Gruppen von Optionsfeldern enthalten, und jede Gruppe sollte mithilfe der folgenden Prozedur hinzugefügt werden.

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld eine Gruppe von Optionsfeldern hinzu

1. Wählen Sie das Optionsfeld-Steuerelement in der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) und wählen Sie den Speicherort in das Dialogfeld, in dem Sie das Steuerelement platzieren möchten.

1. Wiederholen Sie Schritt 1, um so viele Optionsfelder hinzuzufügen, wie Sie benötigen. Stellen Sie sicher, dass die Optionsfelder in der Gruppe in der Aktivierreihenfolge aufeinander folgen.

1. Legen Sie im Fenster [Eigenschaften](/visualstudio/ide/reference/properties-window)die Eigenschaft **Gruppe** des *ersten* Optionsfelds in der Aktivierreihenfolge auf **Wahr**fest.

   Durch das Ändern der Eigenschaft **Gruppe** auf **Wahr** wird dem Eintrag des Felds im Dialogfeld des Ressourcenscripts die Formatvorlage „WS_GROUP“ hinzugefügt und so sichergestellt, dass ein Benutzer immer nur ein Optionsfeld in der Feldgruppe aktivieren kann (wenn der Benutzer auf ein Optionsfeld klickt, werden die anderen in der gleichen Gruppe deaktiviert).

   > [!NOTE]
   > Die Eigenschaft **Gruppe** sollte nur für das erste Optionsfeld einer Gruppe auf **Wahr**festgelegt werden. Wenn Sie über weitere Steuerelemente verfügen, die nicht Teil der Optionsfeldgruppe sind, legen Sie die Eigenschaft **Gruppe** des ersten Steuerelements, *das sich außerhalb der Gruppe befindet* , ebenfalls auf **Wahr** fest. Sie können das erste Steuerelement außerhalb der Gruppe schnell identifizieren, durch Drücken von **STRG**+**D** auf die Aktivierreihenfolge anzuzeigen.

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>So fügen Sie eine Membervariable für die Optionsfeldgruppe hinzu

1. Klicken Sie auf das erste Optionsfeld-Steuerelement in der Aktivierreihenfolge (das dominante Steuerelement, dessen Eigenschaft **Gruppe** auf „Wahr“ festgelegt ist).

1. Wählen Sie im Kontextmenü **Variable hinzufügen** aus.

1. Aktivieren Sie im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)das Kontrollkästchen **Steuerungsvariable** , und aktivieren Sie dann das Optionsfeld **Wert** .

1. Geben Sie im Feld **Variablenname** einen Namen für die neue Membervariable ein.

1. In der **Variablentyp** wählen Sie im Listenfeld **Int** oder `int`.

1. Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Z. B. `m_radioBox1 = 0;` wählt das erste Optionsfeld in der Gruppe.

## <a name="to-align-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

1. Wählen Sie die Steuerelemente, die Sie ausrichten möchten. Achten Sie darauf, um das Steuerelement auszuwählen, die das dominante Steuerelement werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen von die Ausrichtung, oder Ändern der Größe Befehl sein.

   Die letzte Position in der Gruppe von Steuerelementen, hängt von der Position des bestimmenden Steuerelements ab. Weitere Informationen zum Auswählen des bestimmenden Steuerelements finden Sie unter [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md).

1. Von der **Format** Menü wählen **ausrichten**, und wählen Sie dann eines der folgenden Ausrichtungen:

   |Wert|Beschreibung|
   |-----|-----------|
   |`Lefts`|Richtet den ausgewählten Steuerelemente linksbündig.|
   |`Centers`|Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt.|
   |`Rights`|Richtet den ausgewählten Steuerelemente entlang der rechten Seite liegen.|
   |`Tops`|Richtet die ausgewählten Steuerelemente an die oberen Ränder.|
   |`Middles`|Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt.|
   |`Bottoms`|Richtet den ausgewählten Steuerelemente an die unteren Rändern.|

### <a name="to-even-the-spacing-between-controls"></a>Sogar den Abstand zwischen Steuerelementen

Die **Dialogfeld** -Editor können Sie an Steuerelemente der Platz gleichmäßig auf die äußersten Steuerelemente ausgewählt.

1. Wählen Sie die Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **gleichmäßig**, und wählen Sie dann eine der folgenden Ausrichtungsbefehle:

   - `Across`: Steuerelemente gleichmäßig zwischen dem äußeren linken und dem äußersten rechten ausgewählten Steuerelement Speicherplatz.

   - `Down`: Speicherplatz Steuerelemente gleichmäßig zwischen dem obersten und untersten Steuerelements ausgewählt.

### <a name="to-center-controls-in-a-dialog-box"></a>Zentrieren von Steuerelementen in einem Dialogfeld

1. Wählen Sie das Steuerelement oder Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **Center im Dialogfeld**, und wählen Sie dann eine der folgenden Aktionen:

   - `Vertical`: die Steuerelemente in das Dialogfeld vertikal zentrieren.

   - `Horizontal`: Steuerelemente im Dialogfeld horizontal zentriert.

### <a name="to-arrange-push-buttons-along-the-right-or-bottom-of-a-dialog-box"></a>Anordnen von Schaltflächen am rechten oder unteren Rand eines Dialogfelds

1. Wählen Sie eine oder mehrere Schaltflächen an.

1. Von der **Format** Menü wählen **Schaltflächen anordnen**, und wählen Sie dann eine der folgenden Aktionen:

   - `Right`: Richtet die Schaltflächen am rechten Rand des Dialogfelds.

   - `Bottom`: Richtet die Schaltflächen am unteren Rand des Dialogfelds.

       Wenn Sie ein Steuerelement als eine Schaltfläche auswählen, wird nicht seine Position beeinflusst.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)