---
title: Dialog Editor (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 827a7610aa919d5349313346ac0bfa80bd0647b0
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264893"
---
# <a name="dialog-editor-c"></a>Dialog Editor (C++)

Die **Dialogfeld** -Editor können Sie zum Erstellen oder Bearbeiten von Dialogfeldressourcen. Sie öffnen den Dialog-Editor durch Doppelklicken auf ein Dialogfeld für die RC-Datei in die **Ressourcenansicht** Fenster (**Ansicht** > **Ressourcenansicht**). Beachten Sie, dass **Ressourcenansicht** ist in Express-Editionen nicht verfügbar.

Einer der ersten Schritte beim Erstellen eines neuen Dialogfelds (oder einer Dialogfeldvorlage) ist das Hinzufügen von Steuerelementen zum Dialogfeld. In der **Dialogfeld** -Editor, ordnen Sie Steuerelemente entsprechend einer bestimmten Größe, Form oder Ausrichtung, oder Sie verschieben sie rund um die Arbeit in das Dialogfeld. Steuerelemente lassen sich darüber hinaus problemlos löschen.

Um ein Dialogfeld später wiederzuverwenden, können Sie es als Vorlage speichern. Auch das Wechseln zwischen dem Entwurf des Dialogfelds und dem Bearbeiten des Codes, mit dem das Feld implementiert wird, ist denkbar einfach.

Der Dialog-Editor bietet zusätzlich die Möglichkeit, die Eigenschaften einzelner oder mehrerer Steuerelemente zu bearbeiten. Sie können die Aktivierreihenfolge ändern, d. h. die Reihenfolge an, bei dem Steuerelemente erhalten, Fokus, wenn die **Registerkarte** gedrückt wird, oder Sie definieren eine Zugriffstaste (Tastenkombination), die Benutzern ermöglicht, wählen Sie ein Steuerelement unter Verwendung der Tastaturfokus. Eine Liste der vordefinierten Zugriffstasten finden Sie unter [Zugriffstasten für den Dialog-Editor](../windows/accelerator-keys-for-the-dialog-editor.md).

Die **Dialogfeld** Editor ermöglicht auch das Ihnen die Verwendung benutzerdefinierter Steuerelemente einschließlich ActiveX-Steuerelemente. Außerdem können [Formularansichten](../mfc/reference/cformview-class.md), [Datensatzansichten](../data/record-views-mfc-data-access.md)oder [Dialogleisten](../mfc/dialog-bars.md)bearbeitet werden.

Ab Visual Studio 2015 wird können den Dialog-Editor Sie dynamische Layouts definieren, die angeben, wie Sie Steuerelemente zum Verschieben und anpassen, wenn der Benutzer die Größe eines Dialogfelds ändert. Weitere Informationen finden Sie unter [Dynamic Layout](../mfc/dynamic-layout.md).

- [Erstellen eines neuen Dialogfelds](../windows/creating-a-new-dialog-box.md)

- [Erstellen eines Dialogfelds, das zur Laufzeit vom Benutzer nicht beendet werden kann](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)

- [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [Testen eines Dialogfelds](../windows/testing-a-dialog-box.md)

- [Problembehandlung beim Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > Bei der Verwendung der **Dialogfeld** -Editor in vielen Fällen können Sie die rechte Maustaste gedrückt, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen klicken.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="dialog-editor-toolbar"></a>Symbolleiste des Dialog-Editors

Beim Öffnen der **Dialogfeld** -Editor in ein C++-Projekt die **Dialog-Editor** Symbolleiste wird automatisch am oberen Rand der Projektmappe angezeigt.

|Symbol|Bedeutung|Symbol|Bedeutung|
|----------|-------------|----------|-------------|
|![Test Dialog button](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Testdialogfeld|![Schaltfläche "horizontal anordnen"](../mfc/media/vcdialogeditoracross.png "VcDialogEditorAcross")|Über|
|![Richten Sie die Schaltfläche "Links"](../mfc/media/vcdialogeditoralignlefts.png "VcDialogEditorAlignLefts")|Nach links ausrichten|![Schaltfläche "vertikal anordnen"](../mfc/media/vcdialogeditordown.png "VcDialogEditorDown")|Nach unten|
|![Rechte Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignrights.png "VcDialogEditorAlignRights")|Nach rechts ausrichten|![Stellen dieselbe Breite Schaltfläche](../mfc/media/vcdialogeditorsamewidth.png "VcDialogEditorSameWidth")|Breite angleichen|
|![Richten Sie die Schaltfläche "nach oben"](../mfc/media/vcdialogeditoraligntops.png "VcDialogEditorAlignTops")|Nach oben ausrichten|![Die gleiche Höhe Schaltfläche stellen](../mfc/media/vcdialogeditormakesameheight.png "VcDialogEditorMakeSameHeight")|Höhe angleichen|
|![Unten ausrichten Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignbottoms.png "VcDialogEditorAlignBottoms")|Nach unten ausrichten|![Stellen dieselbe Größe Schaltfläche](../mfc/media/vcdialogeditorsamesize.png "VcDialogEditorSameSize")|Größe angleichen|
|![Schaltfläche "Vertikal zentrieren"](../mfc/media/vcdialogeditorvertical.png "VcDialogEditorVertical")|Vertikal|![Raster der Umschaltfläche](../mfc/media/vcdialogeditortogglegrid.png "VcDialogEditorToggleGrid")|Raster umschalten|
|![Schaltfläche "Horizontal zentrieren"](../mfc/media/vcdialogeditorhorizontal.png "VcDialogEditorHorizontal")|Horizontal|![Führungslinien Umschaltfläche](../mfc/media/vcdialogeditortoggleguides.png "VcDialogEditorToggleGuides")|Führungslinien ein-/ausschalten|

Die **Dialog-Editor** Symbolleiste enthält Schaltflächen zum Anordnen des Layouts von Steuerelementen auf der das Dialogfeld, z. B. Größe und Ausrichtung. **Dialog-Editor** Symbolleisten-Schaltflächen entsprechen den Befehlen für die **Format** Menü.

Wenn Sie sind der **Dialogfeld** -Editor können Sie die Anzeige der Umschalten der **Dialog-Editor** Symbolleiste, indem Sie ihn aus der Liste der verfügbaren Symbolleisten und Fenstern auswählen.

- Zum Anzeigen oder Ausblenden der Symbolleiste des Dialog-Editor, auf die **Ansicht** , wählen Sie im Menü **Symbolleisten**, wählen Sie dann **Dialog-Editor** aus dem Untermenü.

   > [!NOTE]
   > Die **Dialog-Editor** Symbolleiste wird standardmäßig angezeigt, wenn Sie eine Dialogfeldressource im Dialog-Editor öffnen, aber wenn Sie explizit auf die Symbolleiste schließen, Sie benötigen es das nächste Mal aufrufen, Sie eine Dialogfeldressource öffnen.

## <a name="switch-between-dialog-box-controls-and-code"></a>Umschalten zwischen Dialogfeld-Steuerelemente und Code

In MFC-Anwendungen Doppelklicken Sie auf der Dialogfeld-Steuerelemente an ihrem Ereignishandlercode zu springen oder schnell Stub Handlerfunktionen erstellen.

Ein Steuerelement ausgewählt ist, und klicken Sie auf die **Steuerelementereignisse** Schaltfläche oder die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) eine vollständige Liste der Windows-Nachrichten und Ereignisse anzeigen für das ausgewählte Element verfügbar. Wählen Sie aus der Liste zum Erstellen oder Bearbeiten von Handlerfunktionen.

- Um Code aus dem Dialog-Editor zu wechseln, doppelklicken Sie auf ein Steuerelement im Dialogfeld, um die Deklaration für die zuletzt implementierter Meldung, die Funktion zur Behandlung zu wechseln. (Für Dialogfeldklassen mit ATL-basiertes ruft Sie immer die Konstruktordefinition.)

- So zeigen Sie Ereignisse für ein Steuerelement, ein Steuerelement ausgewählt ist, wählen Sie die **Steuerelementereignisse** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

   > [!NOTE]
   > Auswählen der **Steuerelementereignisse** Schaltfläche, wenn die *Dialogfeld* verfügt über eine Liste aller Steuerelemente den Fokus verfügbar macht, in das Dialogfeld, das Sie dann so bearbeiten Sie die Ereignisse für die einzelnen Steuerelemente erweitern können.

   Wenn ein einzelnes Steuerelement den Fokus in das Dialogfeld besitzt, können Sie Maustaste und wählen **Ereignishandler hinzufügen** aus dem Kontextmenü. Dadurch können Sie die Klasse an, die der Handler hinzugefügt wird. Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).

- Wählen Sie zum Anzeigen von Meldungen für ein Dialogfeld, mit dem Dialogfeld ausgewählt haben, die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

## <a name="accelerator-keys"></a>Zugriffstasten

Im folgenden sind die Tastenkombinationen für die Dialogfeld-Editor-Befehle. Wählen Sie zum Ändern von Tastenkombinationen **Optionen** auf die **Tools** im Menü Wählen Sie dann **Tastatur** unter der **Umgebung** Ordner. Weitere Informationen finden Sie unter [Identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> Die in einem Dialogfeld verfügbaren Optionen sowie die Namen und Positionen der angezeigten Menübefehle können sich je nach den persönlichen aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Optionen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

|Befehl|Tasten|Beschreibung|
|-------------|----------|-----------------|
|Format.AlignBottoms|**STRG** + **UMSCHALT** + **nach unten zeigenden Pfeil**|Richtet den unteren Rand der ausgewählten Steuerelemente des bestimmenden Steuerelements|
|Format.AlignCenters|**Shift** + **F9**|Richtet die vertikale Mittelpunkte der ausgewählten Steuerelemente mit des bestimmenden Steuerelements|
|Format.AlignLefts|**STRG** + **UMSCHALT** + **Pfeil nach links**|Richtet den linken Rand der ausgewählten Steuerelemente des bestimmenden Steuerelements|
|Format.AlignMiddles|**F9**|Richtet die horizontale Mittelpunkte der ausgewählten Steuerelemente mit des bestimmenden Steuerelements|
|Format.AlignRights|**STRG** + **UMSCHALT** + **-rechts-Taste**|Richtet den rechten Rand der ausgewählten Steuerelemente des bestimmenden Steuerelements|
|Format.AlignTops|**STRG** + **UMSCHALT** + **Pfeil nach oben**|Richtet den oberen Rand der ausgewählten Steuerelemente des bestimmenden Steuerelements|
|Format.ButtonBottom|**Ctrl** + **B**|Stellen Sie die ausgewählten Schaltflächen unten in der Mitte des Dialogfelds|
|Format.ButtonRight|**Ctrl** + **R**|Stellen Sie die ausgewählten Schaltflächen in der oberen rechten Ecke des Dialogfelds|
|Format.CenterHorizontal|**Ctrl** + **Shift** + **F9**|Die Steuerelemente im Dialogfeld horizontal zentriert|
|Format.CenterVertical|**STRG** + **F9**|Die Steuerelemente im Dialogfeld vertikal zentriert|
|Format.CheckMnemonics|**Ctrl** + **M**|Überprüft die Eindeutigkeit von Zugriffstasten|
|Format.SizeToContent|**Shift** + **F7**|Ändert die Größe der ausgewählten Steuerelemente entsprechend den Beschriftungstext|
|Format.SpaceAcross|**ALT** + **NACH-LINKS-TASTE**|Die ausgewählten Steuerelemente horizontal in gleichmäßigen Abständen an.|
|Format.SpaceDown|**ALT** + **nach unten zeigenden Pfeil**|Die ausgewählten Steuerelemente vertikal in gleichmäßigen Abständen an.|
|Format.TabOrder|**STRG** + **D**|Die Reihenfolge der Steuerelemente innerhalb des Dialogfelds festgelegt|
|Format.TestDialog|**STRG** + **T**|Führt das Dialogfeld, um die Darstellung und Verhalten zu testen.|
|Format.ToggleGuides|**STRG** + **G**|Wechselt zwischen keine Raster, Richtlinien und Raster für die Bearbeitung von Dialogfeld|

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)<br/>
[Steuerelementklassen](../mfc/control-classes.md)<br/>
[Dialogfeldklassen](../mfc/dialog-box-classes.md)<br/>
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)