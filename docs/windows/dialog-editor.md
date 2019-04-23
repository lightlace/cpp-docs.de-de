---
title: Dialog Editor (C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
- vc.editors.dialog
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
- Dialog Editor [C++], shortcut keys
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
ms.openlocfilehash: dc5a823951e07af96efceec52d2aa23552c2d002
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029485"
---
# <a name="dialog-editor-c"></a>Dialog Editor (C++)

Die **Dialog-Editor** können Sie zum Erstellen oder Bearbeiten von Dialogfeldressourcen.

- Um den Editor zu öffnen, doppelklicken Sie auf die RC-Datei in einem Dialogfeld auf die **Ressourcenansicht** -Fenster verwenden, oder wechseln Sie zum Menü **Ansicht** > **Ressourcenansicht**.

Einer der ersten Schritte bei der Erstellung ein neues Dialogfeld oder eine Dialogfeldvorlage, hinzufügen Steuerelemente. In der **Dialog-Editor**, Steuerelemente an eine bestimmte Größe, Form oder Ausrichtung anpassen können angeordnet werden, oder Sie können sie rund um die Arbeit in das Dialogfeld verschieben. Steuerelemente lassen sich darüber hinaus problemlos löschen.

Um ein Dialogfeld später wiederzuverwenden, können Sie es als Vorlage speichern. Auch das Wechseln zwischen dem Entwurf des Dialogfelds und dem Bearbeiten des Codes, mit dem das Feld implementiert wird, ist denkbar einfach.

Es ist auch möglich, so bearbeiten Sie die Eigenschaften einzelner oder mehrerer Steuerelemente in der **Dialog-Editor**. Sie können die Aktivierreihenfolge ändern, d. h. die Reihenfolge an, bei dem Steuerelemente erhalten, Fokus, wenn die **Registerkarte** gedrückt wird, oder Sie können definieren, eine Zugriffstaste oder Tastenkombination, die Benutzern ermöglicht, wählen Sie ein Steuerelement unter Verwendung der Tastaturfokus.

Die **Dialog-Editor** ermöglicht auch das Verwenden benutzerdefinierter Steuerelemente einschließlich ActiveX-Steuerelemente. Sie können auch Bearbeiten einer [Formularansicht](../mfc/reference/cformview-class.md), [aufzeichnen Ansichten](../data/record-views-mfc-data-access.md), oder [Dialogleisten](../mfc/dialog-bars.md).

Ab Visual Studio 2015, können Sie die **Dialog-Editor** so definieren Sie dynamische Layouts, die angeben, wie die Steuerelemente verschoben und Ändern der Größe ein, wenn der Benutzer die Größe eines Dialogfelds ändert. Weitere Informationen finden Sie unter [Dynamic Layout](../mfc/dynamic-layout.md).

Weitere Informationen zu Ressourcen finden Sie unter Vorgehensweise [erstellen Sie ein Dialogfeld](../windows/creating-a-new-dialog-box.md) und [Dialogfeld-Steuerelemente](../windows/controls-in-dialog-boxes.md).

> [!TIP]
> Bei der Verwendung der **Dialog-Editor**, in vielen Fällen können Sie mit der rechten Maustaste auswählen, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen.

## <a name="dialog-editor-toolbar"></a>Symbolleiste des Dialog-Editors

Die **Dialog-Editor** Symbolleiste enthält Schaltflächen zum Anordnen des Layouts von Steuerelementen auf der das Dialogfeld, z. B. Größe und Ausrichtung. **Dialog-Editor** Symbolleisten-Schaltflächen entsprechen den Befehlen für die **Format** Menü.

|Symbol|Bedeutung|Symbol|Bedeutung|
|----------|-------------|----------|-------------|
|![Test Dialog button](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Testdialogfeld|![Schaltfläche "horizontal anordnen"](../mfc/media/vcdialogeditoracross.png "VcDialogEditorAcross")|Über|
|![Richten Sie die Schaltfläche "Links"](../mfc/media/vcdialogeditoralignlefts.png "VcDialogEditorAlignLefts")|Nach links ausrichten|![Schaltfläche "vertikal anordnen"](../mfc/media/vcdialogeditordown.png "VcDialogEditorDown")|Nach unten|
|![Rechte Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignrights.png "VcDialogEditorAlignRights")|Nach rechts ausrichten|![Stellen dieselbe Breite Schaltfläche](../mfc/media/vcdialogeditorsamewidth.png "VcDialogEditorSameWidth")|Breite angleichen|
|![Richten Sie die Schaltfläche "nach oben"](../mfc/media/vcdialogeditoraligntops.png "VcDialogEditorAlignTops")|Nach oben ausrichten|![Die gleiche Höhe Schaltfläche stellen](../mfc/media/vcdialogeditormakesameheight.png "VcDialogEditorMakeSameHeight")|Höhe angleichen|
|![Unten ausrichten Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignbottoms.png "VcDialogEditorAlignBottoms")|Nach unten ausrichten|![Stellen dieselbe Größe Schaltfläche](../mfc/media/vcdialogeditorsamesize.png "VcDialogEditorSameSize")|Größe angleichen|
|![Schaltfläche "Vertikal zentrieren"](../mfc/media/vcdialogeditorvertical.png "VcDialogEditorVertical")|Vertikal|![Raster der Umschaltfläche](../mfc/media/vcdialogeditortogglegrid.png "VcDialogEditorToggleGrid")|Raster umschalten|
|![Schaltfläche "Horizontal zentrieren"](../mfc/media/vcdialogeditorhorizontal.png "VcDialogEditorHorizontal")|Horizontal|![Führungslinien Umschaltfläche](../mfc/media/vcdialogeditortoggleguides.png "VcDialogEditorToggleGuides")|Führungslinien ein-/ausschalten|

- Anzeigen oder Ausblenden der **Dialog-Editor** Symbolleiste wechseln Sie zum Menü **Ansicht** > **Symbolleisten** > **Dialog-Editor**.

Beim Öffnen der **Dialog-Editor** in einem C++-Projekt die **Dialog-Editor** Symbolleiste am oberen Rand der Projektmappe automatisch angezeigt wird, jedoch, wenn Sie explizit auf die Symbolleiste schließen, müssen Sie es Aufrufen der Beim nächsten Öffnen der **Dialog-Editor**. Sie können die Anzeige umschalten, indem Sie ihn aus der Liste der verfügbaren Symbolleisten und Fenstern auswählen.

## <a name="switch-between-dialog-box-controls-and-code"></a>Umschalten zwischen Dialogfeld-Steuerelemente und Code

In MFC-Anwendungen Doppelklicken Sie auf der Dialogfeld-Steuerelemente an ihrem Ereignishandlercode zu springen oder schnell Stub Handlerfunktionen erstellen.

Wählen Sie ein Steuerelement ausgewählt ist, die **Steuerelementereignisse** Schaltfläche oder die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) eine vollständige Liste der Windows-Nachrichten und Ereignisse anzeigen für das ausgewählte Element verfügbar. Wählen Sie aus der Liste zum Erstellen oder Bearbeiten von Handlerfunktionen.

- Springen zu Code aus der **Dialog-Editor**, doppelklicken Sie auf ein Steuerelement im Dialogfeld, um die Deklaration für die zuletzt implementierter Meldung, die Funktion zur Behandlung zu wechseln.

   Für Dialogfeldklassen mit ATL-basiertes ruft Sie immer die Konstruktordefinition.

- So zeigen Sie Ereignisse für ein Steuerelement, ein Steuerelement ausgewählt ist, wählen Sie die **Steuerelementereignisse** Schaltfläche der **Eigenschaften** Fenster.

   Wenn ein einzelnes Steuerelement den Fokus in das Dialogfeld besitzt, können Sie mit der rechten Maustaste und wählen Sie **Ereignishandler hinzufügen**. Dadurch können Sie die Klasse an, die der Handler hinzugefügt wird. Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).

   > [!NOTE]
   > Auswählen der **Steuerelementereignisse** Schaltfläche, wenn Sie das Dialogfeld den Fokus besitzt, stellt eine Liste aller Steuerelemente in das Dialogfeld, das Sie dann so bearbeiten Sie die Ereignisse für die einzelnen Steuerelemente erweitern können.

- Wählen Sie zum Anzeigen von Meldungen für ein Dialogfeld, mit dem Dialogfeld ausgewählt haben, die **Nachrichten** Schaltfläche der **Eigenschaften** Fenster.

## <a name="accelerator-keys"></a>Zugriffstasten

Im folgenden sind die Standardeinstellungen für Zugriffstasten für den **Dialog-Editor** Befehle.  

|Befehl|Tasten|Beschreibung|
|-------------|----------|-----------------|
|Format.AlignBottoms|**STRG** + **UMSCHALT** + **nach unten zeigenden Pfeil**|Richtet den unteren Rand der ausgewählten Steuerelemente mit des bestimmenden Steuerelements an.|
|Format.AlignCenters|**Shift** + **F9**|Richtet die ausgewählten Steuerelemente mit des bestimmenden Steuerelements vertikal mittig an.|
|Format.AlignLefts|**STRG** + **UMSCHALT** + **Pfeil nach links**|Ausrichtung am linken Rand der ausgewählten Steuerelemente des bestimmenden Steuerelements an.|
|Format.AlignMiddles|**F9**|Richtet die horizontal mittig in der ausgewählten Steuerelemente an das dominante Steuerelement aus.|
|Format.AlignRights|**STRG** + **UMSCHALT** + **-rechts-Taste**|Richtet den rechten Rand der ausgewählten Steuerelemente mit des bestimmenden Steuerelements an.|
|Format.AlignTops|**STRG** + **UMSCHALT** + **Pfeil nach oben**|Richtet den oberen Ecken der ausgewählten Steuerelemente an das dominante Steuerelement.|
|Format.ButtonBottom|**Ctrl** + **B**|Stellen Sie die ausgewählten Schaltflächen unten in der Mitte des Dialogfelds.|
|Format.ButtonRight|**Ctrl** + **R**|Stellen Sie die ausgewählten Schaltflächen in der oberen rechten Ecke des Dialogfelds.|
|Format.CenterHorizontal|**Ctrl** + **Shift** + **F9**|Zentriert die Steuerelemente horizontal innerhalb des Dialogfelds.|
|Format.CenterVertical|**STRG** + **F9**|Zentriert die Steuerelemente vertikal innerhalb des Dialogfelds.|
|Format.CheckMnemonics|**Ctrl** + **M**|Überprüft die Eindeutigkeit von Zugriffstasten.|
|Format.SizeToContent|**Shift** + **F7**|Ändert die Größe der ausgewählten Steuerelemente entsprechend den Beschriftungstext.|
|Format.SpaceAcross|**ALT** + **NACH-LINKS-TASTE**|Die ausgewählten Steuerelemente gleichmäßigen horizontal.|
|Format.SpaceDown|**ALT** + **nach unten zeigenden Pfeil**|Die ausgewählten Steuerelemente gleichmäßigen vertikal.|
|Format.TabOrder|**STRG** + **D**|Legt die Reihenfolge der Steuerelemente innerhalb des Dialogfelds fest.|
|Format.TestDialog|**STRG** + **T**|Führt das Dialogfeld, um die Darstellung und Verhalten zu testen.|
|Format.ToggleGuides|**STRG** + **G**|Wechselt zwischen keine Raster, Richtlinien und Raster für das Dialogfeld zu bearbeiten.|

- Um Tastenkombinationen zu ändern, wechseln Sie zum Menü **Tools** > **Optionen**, und wählen Sie **Tastatur** unter der **Umgebung** Ordner.

   Weitere Informationen finden Sie unter [Identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

- Um Ihre Einstellungen zu ändern, wechseln Sie zum Menü **Tools** > **Einstellungen importieren und exportieren**.

   Die verfügbaren Optionen in Dialogfeldern und die Namen und die Positionen von Menübefehlen, die Sie sehen, unterscheiden sich von den Beschreibungen in **Hilfe** je nach den aktiven Einstellungen oder der Edition.  Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Vorgehensweise: Erstellen eines Dialogfelds](../windows/creating-a-new-dialog-box.md)<br/>
[Dialogfeldsteuerelemente](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->