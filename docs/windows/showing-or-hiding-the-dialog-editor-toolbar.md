---
title: Ein- oder Ausblenden der Symbolleiste des Dialog-Editor (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
ms.openlocfilehash: e025f560a47f85d17b8c56a4db19f322069d33ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631087"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar-c"></a>Ein- oder Ausblenden der Symbolleiste des Dialog-Editor (C++)

Beim Öffnen der **Dialogfeld** -Editor in ein C++-Projekt die **Dialog-Editor** Symbolleiste wird automatisch am oberen Rand der Projektmappe angezeigt.

### <a name="dialog-editor-toolbar"></a>Symbolleiste des Dialog-Editors

|Symbol|Bedeutung|Symbol|Bedeutung|
|----------|-------------|----------|-------------|
|![Schaltfläche "Testdialogfeld"](../mfc/media/vcdialogeditortestdialog.png "VcDialogEditorTestDialog")|Testdialogfeld|![Schaltfläche "horizontal anordnen"](../mfc/media/vcdialogeditoracross.png "VcDialogEditorAcross")|Über|
|![Richten Sie die Schaltfläche "Links"](../mfc/media/vcdialogeditoralignlefts.png "VcDialogEditorAlignLefts")|Nach links ausrichten|![Schaltfläche "vertikal anordnen"](../mfc/media/vcdialogeditordown.png "VcDialogEditorDown")|Nach unten|
|![Rechte Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignrights.png "VcDialogEditorAlignRights")|Nach rechts ausrichten|![Stellen dieselbe Breite Schaltfläche](../mfc/media/vcdialogeditorsamewidth.png "VcDialogEditorSameWidth")|Breite angleichen|
|![Richten Sie die Schaltfläche "nach oben"](../mfc/media/vcdialogeditoraligntops.png "VcDialogEditorAlignTops")|Nach oben ausrichten|![Die gleiche Höhe Schaltfläche stellen](../mfc/media/vcdialogeditormakesameheight.png "VcDialogEditorMakeSameHeight")|Höhe angleichen|
|![Unten ausrichten Schaltfläche ausrichten](../mfc/media/vcdialogeditoralignbottoms.png "VcDialogEditorAlignBottoms")|Nach unten ausrichten|![Stellen dieselbe Größe Schaltfläche](../mfc/media/vcdialogeditorsamesize.png "VcDialogEditorSameSize")|Größe angleichen|
|![Schaltfläche "Vertikal zentrieren"](../mfc/media/vcdialogeditorvertical.png "VcDialogEditorVertical")|Vertikal|![Raster der Umschaltfläche](../mfc/media/vcdialogeditortogglegrid.png "VcDialogEditorToggleGrid")|Raster umschalten|
|![Schaltfläche "Horizontal zentrieren"](../mfc/media/vcdialogeditorhorizontal.png "VcDialogEditorHorizontal")|Horizontal|![Führungslinien Umschaltfläche](../mfc/media/vcdialogeditortoggleguides.png "VcDialogEditorToggleGuides")|Führungslinien ein-/ausschalten|

Die **Dialog-Editor** Symbolleiste enthält Schaltflächen zum Anordnen des Layouts von Steuerelementen auf der das Dialogfeld, z. B. Größe und Ausrichtung. **Dialog-Editor** Symbolleisten-Schaltflächen entsprechen den Befehlen für die **Format** Menü. Weitere Informationen finden Sie unter [Zugriffstasten für den Dialog-Editor](../windows/accelerator-keys-for-the-dialog-editor.md).

Wenn Sie sind der **Dialogfeld** -Editor können Sie die Anzeige der Umschalten der **Dialog-Editor** Symbolleiste, indem Sie ihn aus der Liste der verfügbaren Symbolleisten und Fenstern auswählen.

### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>Zum Anzeigen oder Ausblenden der Symbolleiste des Dialog-editor

1. Auf der **Ansicht** klicken Sie im Menü **Symbolleisten** wählen Sie dann **Dialog-Editor** aus dem Untermenü.

   > [!NOTE]
   > Die **Dialog-Editor** Symbolleiste wird standardmäßig angezeigt, wenn Sie eine Dialogfeldressource im Dialog-Editor öffnen, aber wenn Sie explizit auf die Symbolleiste schließen, Sie benötigen es das nächste Mal aufrufen, Sie eine Dialogfeldressource öffnen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)