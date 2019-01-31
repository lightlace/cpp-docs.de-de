---
title: Dialog-Editor-Status (Führungslinien und Raster) (C++)
ms.date: 11/04/2016
helpviewer_keywords:
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
ms.assetid: dbacf9ef-e8b0-4125-a7ce-84911c482e98
ms.openlocfilehash: 52fc19d8a39680c16692177e2758fba78afc7d3a
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484993"
---
# <a name="dialog-editor-states-guides-and-grids-c"></a>Dialog-Editor-Status (Führungslinien und Raster) (C++)

Sie können Anordnen von Steuerelementen in Dialogfeldern, mit der **Dialogfeld** -Editor in einer von drei verschiedenen Zuständen:

- Mit dem Führungslinien und Ränder auf (Standardeinstellung)

- Mit das Layoutraster für

- Ohne jegliche Features andocken oder Ausrichtung

Die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) enthält Schaltflächen, die den Status zu steuern. Klicken Sie auf das entsprechende Symbol, um den Status zu ändern. Sie können auch die Status ändern, mit der **Einstellungen für Führungslinien** Befehl die **Format** Menü.

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

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="create-and-set-guides-and-margins"></a>Erstellen und Festlegen von Führungslinien und Rändern

Ob verlagern Sie Steuerelemente, Hinzufügen von Steuerelementen, oder den aktuellen Layout neu anordnen, Anleitungen helfen ausrichten Sie Steuerelemente in einem Dialogfeld genau. Anleitungen, die als blaue gepunktete Linien angezeigt, über das Dialogfeld angezeigt, die im Editor, und entsprechende Pfeile in der Lineale am oberen und am linken Rand der **Dialogfeld** Editor.

Wenn Sie ein Dialogfeld erstellen, werden vier Ränder bereitgestellt. Ränder werden geänderte Anleitungen, die als blaue gepunktete Linien angezeigt werden.

### <a name="to-create-a-guide"></a>Um eine Anleitung zu erstellen.

Dem Lineal klicken Sie auf einmal, um eine Anleitung zu erstellen. (Nur einem Klick erstellt ein neues Handbuch; Doppelklicken startet die **Einstellungen für Führungslinien** Dialogfeld, in dem Sie Einstellungen für Führungslinien angeben können.)

### <a name="to-set-a-guide"></a>Eine Führungslinie festlegen

Klicken Sie auf das Dialogfeld klicken Sie auf der Anleitung, und ziehen Sie es an eine neue Position. (Sie können auch den Pfeil in der zugehörigen Handbuch ziehen das Lineal klicken.)

Die Koordinaten des Handbuchs werden in der Statusleiste am unteren Rand des Fensters und auf dem Lineal angezeigt. Zeigen Sie auf den Pfeil auf das Lineal, um die genaue Position des Handbuchs anzuzeigen.

### <a name="to-delete-a-guide"></a>So löschen Sie eine Führungslinie

Ziehen Sie das Handbuch aus das Dialogfeld ein.

\- oder –

Ziehen Sie die entsprechenden Pfeil vom Lineal.

### <a name="to-move-margins"></a>So verschieben Sie Ränder

Ziehen Sie den Rand auf die neue Position ein.

Um einen Rand zu machen, verschieben Sie den Rand zu einer Position 0 (null). Klicken Sie zum Wiederherstellen des Rands, platzieren Sie den Mauszeiger über des Rands der Nullposition, und verschieben Sie den Rand in Position.

## <a name="align-controls-on-a-guide"></a>Ausrichten von Steuerelementen an einer Führungslinie

Die Ziehpunkte des Steuerelementen ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Anleitungen an Steuerelemente ausrichten, wenn keine zuvor im Handbuch angedockte Steuerelemente enthalten sind. Wenn eine Anleitung verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die an mehr als ein Handbuch Rasterlinie ausgerichtet werden geändert, wenn eine der Anleitungen verschoben wird.

Die Teilstriche in die Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU ist die durchschnittliche Höhe der Schriftart geteilt durch acht.

### <a name="to-size-a-group-of-controls-with-guides"></a>Eine Gruppe von Steuerelementen mit Guides Größe

1. Richten Sie eine Seite des Steuerelements (oder Steuerelemente), um eine Anleitung.

1. Ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente).

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

1. Verschieben Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente).

### <a name="to-change-the-intervals-of-the-tick-marks"></a>So ändern Sie die Intervalle der Teilstriche

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld die **Rasterweite** an eine neue Breite und Höhe in DLUs.

## <a name="disable-guides"></a>Deaktivieren von Führungslinien

Sie können spezielle Schlüssel in Verbindung mit der Maus verwenden, so deaktivieren Sie die Andocken Auswirkungen der Anleitungen. Mithilfe der **Alt** Schlüssel deaktiviert die Andocken Auswirkungen des Handbuchs ausgewählt. Verschieben eine Anleitung mit den **UMSCHALT** Schlüssel wird verhindert, dass Steuerelemente automatisch auszurichten mit dem für das verschieben.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>So deaktivieren Sie die Andocken Auswirkungen der Anleitungen

Ziehen Sie das Steuerelement bei gedrückter der **Alt** Schlüssel.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Handbücher zu verschieben, ohne dass die angedockte Steuerelemente verschoben

Ziehen Sie die Führungslinie bei gedrückter der **UMSCHALT** Schlüssel.

### <a name="to-turn-off-the-guides"></a>So deaktivieren Sie die Handbücher

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld **Layoutführungslinien**Option **keine**.

   > [!NOTE]
   > Sie können auch den Zugriff auf die Lineal-Leiste doppelklicken dem **Einstellungen für Führungslinien** Dialogfeld.

\- oder –

Auf der **Format** , wählen Sie im Menü **Führungslinien ein-/ausschalten**.

## <a name="modify-the-layout-grid"></a>Ändern des Layoutrasters

Beim platzieren oder Anordnen von Steuerelementen in einem Dialogfeld, können Sie das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, scheinen die Steuerelemente ", die gepunkteten Zeilen im Raster ausrichten" einzurasten. Sie können Aktivieren dieses Feature "am Raster ausrichten" ein, und deaktivieren und Ändern der Größe der Rasterzellen des Layouts.

### <a name="to-turn-the-layout-grid-on-or-off"></a>Zum Aktivieren oder deaktivieren Sie des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialogfeld** -Editor-Fenster mit den **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

### <a name="to-change-the-size-of-the-layout-grid"></a>Ändern die Größe des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

1. In der **Einstellungen für Führungslinien** Dialogfeld geben die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4 DLUs. Weitere Informationen zu DLUs, finden Sie unter [Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente (MFC)](../mfc/controls-mfc.md)<br/>
