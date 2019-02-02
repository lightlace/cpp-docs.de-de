---
title: Symbolleiste (Bildbearbeitung für Symbole C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.texttool
helpviewer_keywords:
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
- toolbars [C++], showing
- toolbars [C++], hiding
- text, adding to an image
- Text Tool dialog box [C++]
- Text Tool Font dialog box [C++]
- fonts, changing on an image
- text, on images
ms.assetid: a0af4209-6273-4106-a7c1-0edecc9b5755
ms.openlocfilehash: dfbd721afd997f3151b1c20a7e0e1fb60e0c83e4
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560321"
---
# <a name="toolbar-c-image-editor-for-icons"></a>Symbolleiste (Bildbearbeitung für Symbole C++)

Die **Bildbearbeitung** Symbolleiste enthält Tools für die Zeichnung zeichnen, Text eingeben, löschen und Bearbeiten von Ansichten. Sie enthält außerdem eine Optionsauswahl, mit der Sie Optionen für die Verwendung jedes Tools auswählen können. Sie können z. B. aus verschiedenen Pinsel breiten Vergrößerungsfaktoren und linienformaten.

> [!NOTE]
> Alle Tools zur Verfügung, auf die **Bild-Editor** Symbolleiste stehen auch über die **Image** Menü (unter der **Tools** Befehl).

![Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbar.gif "VcImageEditorToolbar") Symbolleiste der Bildbearbeitung

Verwenden der **Bildbearbeitung** Symbolleiste und **Option** Auswahl, wählen Sie das Tool oder option werden sollen.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

Mit der **Option** Auswahl können Sie die Breite einer Zeile, Pinselstrich usw. angeben. Das Symbol auf der **Option** Selektor Schaltfläche ändert sich je nachdem welches Tool Sie ausgewählt haben.

![Zeichnen von&#45;Shape-Selektor auf der Symbolleiste der Bildbearbeitung](../mfc/media/vcimageeditortoolbaroptionselector.gif "VcImageEditorToolbarOptionSelector") Optionsauswahl auf der Symbolleiste der Bildbearbeitung

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="use-the-text-tool-dialog-box"></a>Verwenden Sie das Dialogfeld "Texttool"

Verwenden der **Texttool** Dialogfeld zum Hinzufügen von Text mit einem Cursor, Bitmap oder Symbol.

Um dieses Dialogfeld zuzugreifen, öffnen die [Bildbearbeitung](../windows/window-panes-image-editor-for-icons.md). Wählen Sie **Tools** aus der **Image** Menü, und wählen Sie dann die **Texttool** Befehl.

### <a name="font-button"></a>Schaltfläche "Schriftart"

Öffnet die **Schriftart für Texttool** Dialogfeld, in dem Sie die Schriftart, Schriftschnitt oder Schriftgrad Cursor ändern können. Änderungen werden angewendet, um den Text in die **Text** Bereich.

Um dieses Dialogfeld zuzugreifen, wählen die **Schriftart** Schaltfläche der **Texttool** Dialogfeld. Die Eigenschaften, die verfügbar sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Schriftart**|Listet die verfügbaren Schriftarten an.|
|**Schriftschnitt**|Listet die verfügbaren Formate für die angegebene Schriftart an.|
|**Size**|Listet die verfügbaren Punktgrößen für die angegebene Schriftart an.|
|**Beispiel**|Zeigt ein Beispiel, wie Text mit den Einstellungen für die angegebene Schriftart angezeigt wird.|
|**Skript**|Listet die verfügbaren Sprachskripts für die angegebene Schriftart. Wenn Sie ein Skript für die andere Sprache auswählen, wird der Zeichensatz für, dass die Sprache für die Erstellung von multilingual Dokumente verfügbar.|

#### <a name="to-change-the-font-of-text-on-an-image"></a>Ändern die Schriftart von Text in einem Bild

Das folgende Verfahren ist ein Beispiel zum Hinzufügen von Text auf ein Symbol in einer Windows-Anwendung, und bearbeiten die Schriftart des Textes.

1. Erstellen einer C++-Windows Forms-Anwendung. Weitere Informationen finden Sie unter [Erstellen eines Windows-Anwendungsprojekts](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5). Ein *app.ico* Datei wird standardmäßig zum Projekt hinzugefügt.

1. In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei *app.ico*. Die [Bildbearbeitung](../windows/image-editor-for-icons.md) wird geöffnet.

1. Von der **Image** , wählen Sie im Menü **Tools** und wählen Sie dann **Texttool**. Die **Texttool** Dialogfeld wird angezeigt.

1. In der **Texttool** (Dialogfeld), Typ *C++* in den leeren Textbereich. Dieser Text wird angezeigt, in einem in der Größe veränderbaren befindet sich in der oberen linken Ecke des *app.ico*in die **Bildbearbeitung**.

1. In der **Bildbearbeitung**, ziehen Sie das Kontrollkästchen in der Größe veränderbaren in der Mitte des app.ico, um die Lesbarkeit von Text zu verbessern.

1. In der **Texttool** wählen Sie im Dialogfeld die **Schriftart** Schaltfläche. Die **Schriftart für Texttool** Dialogfeld wird angezeigt.

1. In der **Schriftart für Texttool** wählen Sie im Dialogfeld **Times New Roman** aus der Liste der verfügbaren Schriftarten, die in aufgeführt sind die **Schriftart** Listenfeld.

1. Wählen Sie **fett** aus der Liste der verfügbaren Schriftschnitte aufgeführt, die der **Schriftschnitt** Listenfeld.

1. Wählen Sie **10** zeigen Sie auf der Liste der verfügbaren Größen der **Größe** Listenfeld.

1. Klicken Sie auf die Schaltfläche **OK**. Die **Schriftart für Texttool** wird das Dialogfeld zu schließen und die schriftarteinstellungen der neuen in den Text gelten.

1. Wählen Sie die **schließen** Schaltfläche der **Texttool** im Dialogfeld. Das Feld mit veränderbarer Größe, um den Text nicht mehr auf die **Bildbearbeitung**.

### <a name="text-area"></a>Textbereich

Zeigt den Text, der als Teil der Ressource angezeigt wird. Dieser Bereich ist zunächst leer.

> [!NOTE]
> Wenn **transparenten Hintergrund** festgelegt ist, wird nur der Text in das Image platziert werden. Wenn **nicht transparenter Hintergrund** festgelegt ist, wird ein umschließendes Rechteck, gefüllt mit dem [Hintergrundfarbe](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), hinter dem Text platziert werden. Weitere Informationen finden Sie unter [Auswählen eines transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Sie können mit der rechten Maustaste auf die **Texttool** im Dialogfeld ein standardmäßigen Kontextmenü zugreifen, die eine Liste der standard-Windows-Befehle enthält.

## <a name="to-display-or-hide-the-image-editor-toolbar"></a>Zum Anzeigen oder Ausblenden der Symbolleiste der Bildbearbeitung

Da viele der Zeichenwerkzeuge aus verfügbar sind die [Tastatur](../windows/accelerator-keys-image-editor-for-icons.md), manchmal ist es sinnvoll, zum Ausblenden der **Bildbearbeitung** Symbolleiste.

Auf der **Ansicht** , wählen Sie im Menü **Symbolleisten** wählen Sie dann **Bildbearbeitung**.

   > [!NOTE]
   > Diese Symbolleiste Elemente aus dem aktuellen Projekt nicht verfügbar, wenn eine Image-Datei angezeigt werden, oder Lösung ist nicht geöffnet, in der **Bildbearbeitung**. Finden Sie unter [erstellen ein Symbol oder andere Bild](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), Weitere Informationen zum Hinzufügen von Bilddateien zu Ihren Projekten.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md)<br/>
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>