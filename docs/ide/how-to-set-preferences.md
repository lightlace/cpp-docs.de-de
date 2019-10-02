---
title: Festlegen der C++ Codierungs Einstellungen in Visual Studio
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: f1d222dc38720ea897cfbf2fb9fa0dd2727e7720
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816349"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Festlegen der C++ Codierungs Einstellungen in Visual Studio

Durch Personalisieren von Visual C++ Studio können Sie Ihre Programmierfunktionen bequemer, produktiver und angenehmer gestalten. Sie haben folgende Möglichkeiten:

- Passen Sie die Menüs und Symbolleisten an.
- Ordnen Sie das Fenster Layout an.
- Legen Sie Farb Designs fest.
- Geben C++ Sie Formatierungs Regeln an, einschließlich verschiedener Stile von clangformat.
- Erstellen Sie benutzerdefinierte Tastenkombinationen.

Sie können Ihre Einstellungen auf mehreren Computern synchronisieren und mehrere Einstellungs Sätze erstellen und speichern und Sie gemeinsam mit Teamkollegen freigeben. Sie können Erweiterungen aus dem Visual Studio Marketplace installieren, sodass Sie zusätzliche Optionen zum Anpassen des Verhaltens bereitstellt. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="arrange-window-layout"></a>Fenster Layout anordnen

Im Visual Studio-Fenster wird der Leerraum in das Hauptmenü, die Symbolleiste, den Code-Editor (oder das Dokument Fenster) und die Tool Fenster (z. b. Projektmappen-Explorer und Fehlerliste) aufgeteilt. Einige Fenster überlappen einander an derselben Position. Beispielsweise haben Projektmappen-Explorer, Klassenansicht, Ressourcenansicht und Quellcodeverwaltungs-Explorer die gleiche Standardposition. Sie wechseln zwischen diesen, indem Sie die Registerkarten am unteren Rand des Frames auswählen. Wenn Sie zwei oder mehr dieser Fenster gleichzeitig sichtbar machen möchten, ziehen Sie eine von Ihnen in der Titelleiste auf eine neue Position. Sie können Sie an einem der Visual Studio-Hauptfenster Rahmen andocken, oder Sie können Sie float.

Der folgende Screenshot zeigt das **Team Explorer** Fenster, das von seiner Standardposition zu einer neuen, angedockten Position auf der linken Seite des Code-Editors gezogen wird. Der blaue schattierte Bereich zeigt an, wo das Fenster platziert wird, wenn die Maustaste losgelassen wird.

![Screenshot von Visual Studio Team Explorer Fenster mit hervorgehobener Layoutänderung](media/window-layout-move-team-explorer.png)

Im Dokument Fenster ist jede geöffnete Datei in einem Frame im Registerkarten Format enthalten. Sie können diese Registerkarten genau wie Tool Fenster float oder sperren. Weitere Informationen finden Sie unter [Anpassen der Fensterlayouts in Visual Studio](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Um alle Tool Fenster auszublenden und das Fenster des Code-Editors zu maximieren, drücken**Sie** **alt** + **UMSCHALT** + , um den *Vollbildmodus*zu wechseln.

## <a name="set-c-coding-styles-and-formatting"></a>Codierungs Stile und Formatierung festlegen C++

Sie können viele einzelne Code Formatierungsoptionen angeben, z. b. Einzug-und Klammer Positionen. Wechseln Sie zu diesem Zweck zu **Extras @no__t-** 1**Optionen** > **Text-Editor**@no__t-**5 CC++/**  > -**Formatierung** (oder geben Sie **STRG + Q** ein, und suchen Sie nach "Formatierung"). Alternativ können Sie einen der [clangformat](https://clang.llvm.org/docs/ClangFormat.html) -Stile angeben (oder ihren eigenen benutzerdefinierten clangformat-Stil).

![Screenshot der clangformat-Optionen](media/clang-format-ide.png)

Weitere Informationen zu allen Formatierungsoptionen finden Sie unter [Optionen, Text-Editor, CC++/, Formatierung](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting).

## <a name="set-the-color-theme"></a>Festlegen des Farbdesigns

Um einen hellen oder dunklen Hintergrund festzulegen, geben Sie **STRG + Q** ein, und suchen Sie nach "Color Theme". Sie finden diese **auch unter Extras @no__t-** 1**Optionen** > **Umgebung**, und wählen Sie **Farb**Design aus.

![Screenshot der Farbschemas](media/tools-options-color-theme.png)

Hier ist beispielsweise das dunkle Design:

![Screenshot von Visual Studio mit dunkel Farben Design](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>Anpassen der Farbgebung von Code

In Visual Studio 2019 können Sie drei vordefinierte *Farbschemas*auswählen. Diese geben an, wie Code Elemente im Editor farbig markiert werden. Wenn Sie ein Design auswählen möchten, **wechseln Sie zu Extras @no__t-** 1**Optionen** > **Text-Editor** > **C/C++**  > **Ansicht**, und wählen Sie **Farbschema**:

![Screenshot der C++ Optionen für Farbschemas mit erweiterter Hervorhebung](media/color-schemes.png)

In dem Farbschema mit dem Namen **Visual Studio 2017**sind die meisten Code Elemente einfach schwarz. Im **erweiterten** Farbschema werden Funktionen, lokale Variablen, Makros und andere Elemente eingefärbt. In den **enhanced (Globals im Vergleich zu Members)** -Schema, sind globale Funktionen und Variablen farbig markiert, um mit den Klassenmembern zu vergleichen. Der Standardmodus ist **erweitert**und sieht wie folgt aus:

![Screenshot des erweiterten Farbschemas](media/color-scheme-enhanced.png)

Unabhängig davon, welches Design-oder Farbschema aktiv ist, können Sie die Schriftart und Farben für einzelne Code Elemente anpassen. Wechseln Sie zu diesem Zweck zu **Extras @no__t-** 1**Optionen** > **Umgebung** > **Schriftarten und Farben** (oder drücken Sie **STRG + Q** , und suchen Sie nach "Fonts"). Scrollen Sie in der Liste der Elemente anzeigen, bis die C++ Optionen angezeigt werden.

![Screenshot der C++ Schriftart-und Farboptionen](media/tools-options-cpp-colors.png)

Farben, die Sie hier festlegen, überschreiben die Werte, die für das Farbschema definiert sind. Wenn Sie zu den Standardfarben für das Farbschema zurückkehren möchten, legen Sie die Farbe auf " **default**" zurück.

## <a name="customize-the-toolbars"></a>Anpassen der Symbolleisten

Die Symbolleisten stellen eine bequeme Möglichkeit dar, Befehle mit nur einem Mausklick auszugeben, anstatt die Menüs oder Tastenkombinationen zu verwenden. Visual Studio enthält einen Standardsatz von Symbolleisten. Bei der C++ Standardentwicklung sind die nützlichsten Symbolleisten wahrscheinlich Standard, Text-Editor, Build, Debug, Quell Code Verwaltung und Dateien vergleichen. Bei der Windows-Entwicklung sind der Dialog-Editor und der Bild-Editor nützlich zum Anordnen von Dialogfeldern und zum Bearbeiten von Symbolen.

Zeigen Sie auf die Symbole auf der Symbolleiste, um den Befehl anzuzeigen, den Sie darstellt:

![Screenshot von Symbolleisten Symbolen mit Beispiel für Befehls Informationen, die auf Hover verfügbar sind](media/toolbar-mouse-hover.png)

Sie können Befehle hinzufügen oder entfernen oder eine benutzerdefinierte Symbolleiste erstellen, indem Sie den Pfeil nach unten auswählen. Um die Symbolleiste an einen neuen Speicherort zu verschieben, ziehen Sie Sie auf der linken Seite an die gepunktete Leiste.

![Screenshot der Symbolleiste mit hervorgehobenem Pfeil nach unten und gepunktete Leiste](media/toolbar-move-edit.png).

Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Menüs und Symbolleisten in Visual Studio @ no__t-0.

## <a name="show-or-hide-line-numbers"></a>Anzeigen oder Ausblenden von Zeilennummern

Sie können angeben, ob die Zeilennummern links neben den Editor Fenstern angezeigt werden. Wählen Sie unter Optionen unter **CC++/** die **Option** **Allgemein**aus. Wählen Sie im Abschnitt **Einstellungen** je nach bevorzugter **Zeilennummern**aus, oder löschen Sie Sie.

![Screenshot der allgemeinen Optionen mit hervorgehobener Zeilennummer](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>Erstellen von Tastenkombinationen

Viele Befehle in Visual Studio verfügen über *Tasten*Kombinationen, Tastenkombinationen mit STRG, alt und Umschalttaste. Sie können diese Tastenkombinationen ändern oder neue in Visual Studio erstellen. Wechseln Sie zu Extras @no__t-**1 Optionen**@no__t-**3 Umgebung** > **Tastatur** (oder geben Sie **STRG + Q** ein, und suchen Sie nach "Verknüpfungen"). Weitere Informationen finden Sie unter [identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).
