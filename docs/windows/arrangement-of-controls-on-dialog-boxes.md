---
title: Anordnung von Steuerelementen in Dialogfeldern (C++) | Microsoft-Dokumentation
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.grouping
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
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: 210fbf8e062b4dd8c469f9c40a015bbc19bc2843
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152741"
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

#### <a name="to-size-a-group-of-controls-with-guides"></a>Eine Gruppe von Steuerelementen mit Guides Größe

1. Richten Sie eine Seite des Steuerelements (oder Steuerelemente), um eine Anleitung.

1. Ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente).

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

1. Verschieben Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente).

#### <a name="to-change-the-intervals-of-the-tick-marks"></a>So ändern Sie die Intervalle der Teilstriche

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld die **Rasterweite** an eine neue Breite und Höhe in DLUs.

### <a name="disable-guides"></a>Deaktivieren von Führungslinien

Sie können spezielle Schlüssel in Verbindung mit der Maus verwenden, so deaktivieren Sie die Andocken Auswirkungen der Anleitungen. Mithilfe der **Alt** Schlüssel deaktiviert die Andocken Auswirkungen des Handbuchs ausgewählt. Verschieben eine Anleitung mit den **UMSCHALT** Schlüssel wird verhindert, dass Steuerelemente automatisch auszurichten mit dem für das verschieben.

#### <a name="to-disable-the-snapping-effect-of-the-guides"></a>So deaktivieren Sie die Andocken Auswirkungen der Anleitungen

Ziehen Sie das Steuerelement bei gedrückter der **Alt** Schlüssel.

#### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Handbücher zu verschieben, ohne dass die angedockte Steuerelemente verschoben

Ziehen Sie die Führungslinie bei gedrückter der **UMSCHALT** Schlüssel.

#### <a name="to-turn-off-the-guides"></a>So deaktivieren Sie die Handbücher

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld **Layoutführungslinien**Option **keine**.

   > [!NOTE]
   > Sie können auch den Zugriff auf die Lineal-Leiste doppelklicken dem **Einstellungen für Führungslinien** Dialogfeld.

\- oder –

Auf der **Format** , wählen Sie im Menü **Führungslinien ein-/ausschalten**.

### <a name="modify-the-layout-grid"></a>Ändern des Layoutrasters

Beim platzieren oder Anordnen von Steuerelementen in einem Dialogfeld, können Sie das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, scheinen die Steuerelemente ", die gepunkteten Zeilen im Raster ausrichten" einzurasten. Sie können Aktivieren dieses Feature "am Raster ausrichten" ein, und deaktivieren und Ändern der Größe der Rasterzellen des Layouts.

#### <a name="to-turn-the-layout-grid-on-or-off"></a>Zum Aktivieren oder deaktivieren Sie des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialogfeld** -Editor-Fenster mit den **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

#### <a name="to-change-the-size-of-the-layout-grid"></a>Ändern die Größe des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld geben die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4 DLUs.

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

## <a name="align-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

Die folgenden Verfahren zeigen, wie zum Ausrichten von Steuerelementen:

### <a name="to-align-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

1. [Wählen Sie die Steuerelemente](../windows/selecting-multiple-controls.md) Sie ausrichten möchten. Achten Sie darauf, um das Steuerelement auszuwählen, die das dominante Steuerelement werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen von die Ausrichtung, oder Ändern der Größe Befehl sein.

   Die letzte Position in der Gruppe von Steuerelementen, hängt von der Position des bestimmenden Steuerelements ab. Weitere Informationen zum Auswählen des bestimmenden Steuerelements finden Sie unter [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md).

1. Von der **Format** Menü wählen **ausrichten**, und wählen Sie dann eines der folgenden Ausrichtungen:

   - `Lefts`: Richtet die ausgewählten Steuerelemente an die linke Seite.

   - `Centers`: Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt aus.

   - `Rights`: Richtet die ausgewählten Steuerelemente an die rechte Seite.

   - `Tops`: Richtet die ausgewählten Steuerelemente an die oberen Ränder.

   - `Middles`: Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt aus.

   - `Bottoms`: Richtet die ausgewählten Steuerelemente an die unteren Rand.

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

## <a name="change-the-tab-order-of-controls"></a>Ändern der Aktivierreihenfolge von Steuerelementen

Die Aktivierreihenfolge ist die Reihenfolge, in der **Registerkarte** -Taste wird den Eingabefokus von einem Steuerelement verschoben, an den nächsten in einem Dialogfeld. In der Regel wird die Aktivierreihenfolge auf, von links nach rechts und von oben nach unten in einem Dialogfeld. Jedes Steuerelement verfügt über eine **Tabstop** -Eigenschaft, die bestimmt, ob ein Steuerelement den Eingabefokus erhält.

### <a name="to-set-input-focus-for-a-control"></a>Eingabefokus für ein Steuerelement festgelegt.

In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)Option **"true"** oder **"false"** in die **Tabstop** Eigenschaft.

Auch Steuerelemente, die nicht die **Tabstop** -Eigenschaftensatz auf **"true"** müssen Teil der Aktivierreihenfolge. Tab-Reihenfolge ist wichtig, z. B., wenn Sie [definieren Sie Zugriffstasten (mnemonischen Zeichen)](../windows/defining-mnemonics-access-keys.md) für Steuerelemente, die keine Beschriftungen haben. Statischer Text, der eine Zugriffstaste für ein verwandtes Steuerelement enthält muss das zugehörige Steuerelement in der Aktivierreihenfolge unmittelbar vorangestellt sein.

> [!NOTE]
> Wenn das Dialogfeld überlappende Steuerelemente enthält, unter Umständen ändern der Aktivierreihenfolge verändern, wie die Steuerelemente angezeigt werden. Steuerelemente, die weiter unten in der Aktivierreihenfolge erläutert werden immer auf überlappende Steuerelemente angezeigt, die ihnen in der Aktivierreihenfolge vorausgehen.

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Anzeigen die aktuellen Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld

Auf der **Format** , wählen Sie im Menü **Aktivierreihenfolge**.

\- oder –

- Drücken Sie **STRG** + **D**.

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>So ändern Sie die Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld

1. Auf der **Format** , wählen Sie im Menü **Aktivierreihenfolge**.

   Eine Zahl in der oberen linken Ecke der einzelnen Steuerelemente zeigt seine Position in der aktuellen Aktivierreihenfolge.

1. Festlegen der Aktivierreihenfolge durch Klicken auf jedes Steuerelement in der gewünschten Reihenfolge der **Registerkarte** Schlüssel folgen.

1. Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.

   > [!TIP]
   > Nach der Eingabe **Aktivierreihenfolge** -Modus können Sie durch Drücken **Esc** oder **EINGABETASTE** So deaktivieren Sie die Möglichkeit zum Ändern der Aktivierreihenfolge.

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>So ändern Sie die Aktivierreihenfolge für zwei oder mehr Steuerelementen

1. Von der **Format** Menü wählen **Aktivierreihenfolge**.

1. Geben Sie die Änderung in der Reihenfolge, in denen beginnt. Halten Sie zunächst die **STRG** Schlüssel wählen Sie das Steuerelement, und wählen Sie diejenige aus, die Reihenfolge geänderte werden sollen.

   Z. B., wenn Sie die Reihenfolge der Steuerelemente ändern möchten `7` über `9`, halten Sie die **STRG**, wählen Sie dann das Steuerelement `6` erste.

   > [!NOTE]
   > Für ein bestimmtes Steuerelement festzulegen, Anzahl `1` (zuerst in der Aktivierreihenfolge), doppelklicken Sie auf das Steuerelement.

1. Version der **STRG** Schlüssel aus, und wählen Sie die Steuerelemente in der gewünschten Reihenfolge der **Registerkarte** -Taste, um von diesem Punkt folgen.

1. Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)