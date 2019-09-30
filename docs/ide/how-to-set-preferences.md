---
title: Festlegen der C++ Codierungs Einstellungen in Visual Studio
ms.description: Customize C++ formatting, colors, layout, line numbers, menus and more in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 90c9f39135b90a2c5015861a78dd8760b9a8aeed
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686947"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Festlegen der C++ Codierungs Einstellungen in Visual Studio

Durch Personalisieren von Visual C++ Studio können Sie Ihre Programmierfunktionen bequemer, produktiver und angenehmer gestalten. Sie können die Menüs und Symbolleisten anpassen, das Fenster Layout anordnen, Farbschemas festlegen C++ , Formatierungs Regeln angeben, einschließlich verschiedener clangformat-Varianten, und benutzerdefinierte Tastenkombinationen erstellen. Sie können Ihre Einstellungen auf mehreren Computern synchronisieren und mehrere Einstellungs Sätze erstellen und speichern und Sie gemeinsam mit Teamkollegen freigeben. Sie können Erweiterungen aus den Visual Studio Marketplace installieren, die ein zusätzliches benutzerdefiniertes Verhalten bereitstellen. Viele dieser Optionen sind unter [Personalisieren der Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)dokumentiert.

## <a name="arrange-window-layout"></a>Fenster Layout anordnen

Im Visual Studio-Fenster wird der Leerraum in das Hauptmenü, die Symbolleiste, den Code-Editor (oder das Dokument Fenster) und die Tool Fenster (**Projektmappen-Explorer**, **Fehlerliste**usw.) aufgeteilt. Einige Fenster überlappen einander an derselben Position. Beispielsweise haben **Projektmappen-Explorer**, **Klassenansicht**, **Ressourcenansicht**und **Quellcodeverwaltungs-Explorer** die gleiche Standardposition. Sie wechseln zwischen diesen durch Klicken auf die Registerkarten am unteren Rand des Frames. Wenn Sie zwei oder mehr dieser Fenster gleichzeitig sichtbar machen möchten, ziehen Sie eine von Ihnen in der Titelleiste auf eine neue Position. Sie können Sie an einem der Visual Studio-Hauptfenster Rahmen andocken, oder Sie können Sie float. In der folgenden Abbildung wird das Fenster **Team Explorer** im Prozess des gedrag von der Standardposition an eine neue angedockte Position auf der linken Seite des Code-Editors gezeigt. Der blaue schattierte Bereich zeigt an, wo das Fenster platziert wird, wenn die Maustaste losgelassen wird.

![Ändern des Fensterlayouts](media/window-layout-move-team-explorer.png)

Im Dokument Fenster ist jede geöffnete Datei in einem Frame im Registerkarten Format enthalten. Sie können diese Registerkarten wie Tool Fenster float oder sperren. Weitere Informationen finden Sie unter [Anpassen der Fensterlayouts in Visual Studio](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Um alle Tool Fenster auszublenden und das Fenster des Code-Editors zu maximieren, drücken**Sie** **alt** + **UMSCHALT** + , um den *Vollbildmodus*zu wechseln.

## <a name="set-c-coding-styles-and-formatting"></a>Codierungs Stile und Formatierung festlegen C++

Sie können viele einzelne Code Formatierungsoptionen angeben, z. b. Einzug-und Klammer Positionen, **indem Sie zu**Extras  > **Optionen** > **Text-Editor** > **C++C/**  > -**Formatierung** (oder Typ) navigieren. **STRG + Q** und suchen Sie nach "Formatierung".) Alternativ können Sie einen der [clangformat](https://clang.llvm.org/docs/ClangFormat.html) -Stile (oder ihren eigenen benutzerdefinierten clangformat-Stil) angeben:

![Clangformat-Optionen](media/clang-format-ide.png)

Weitere Informationen zu allen Formatierungsoptionen finden Sie unter [Optionen, Text-Editor, CC++/, Formatierung](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting).

## <a name="set-the-color-theme"></a>Festlegen des Farbdesigns

Um einen hellen oder dunklen Hintergrund festzulegen, geben Sie **STRG + Q** ein, und suchen Sie nach "Color Theme". Sie können dort auch über **Tools** > -**Optionen** > -**Umgebung** und **Farb**Design auswählen:

![Farb Designs](media/tools-options-color-theme.png)

Die folgende Abbildung zeigt das dunkle Design:

![Dunkles Design](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>Anpassen der Farbgebung von Code

In Visual Studio 2019 können Sie drei vordefinierte *Farbschemas* auswählen, die angeben, wie Code Elemente im Editor eingefärbt werden. Um ein Design auszuwählen, navigieren Sie **zu Extras @no__t-** 1**Optionen** > **Text-Editor** > **C/C++**  > **Ansicht** , und wählen Sie **Farbschema**:

![C++Farbschemas](media/color-schemes.png)

Im **Visual Studio 2017** -Farbschema sind die meisten Code Elemente einfach schwarz. Im **erweiterten** Farbschema werden Funktionen, lokale Variablen, Makros und andere Elemente eingefärbt. In den **enhanced (Globals im Vergleich zu Members)** -Schema, sind globale Funktionen und Variablen farbig markiert, um mit den Klassenmembern zu vergleichen. Der Standardmodus ist **erweitert** und sieht wie folgt aus:

![Verbessertes Farbschema](media/color-scheme-enhanced.png)

Unabhängig davon, welches Design-oder Farbschema aktiv ist, können Sie die Schriftart und Farben für einzelne Code Elemente **anpassen, indem Sie zu Extras** > **Optionen** > **Umgebung** > **Schriftarten und Farben** (oder Typ **) navigieren. STRG + Q** und suchen nach "Fonts"). Führen Sie C++ einen Bildlauf nach unten in der Liste der Elemente anzeigen durch

![C++Schriftart-und Farboptionen](media/tools-options-cpp-colors.png)

Farben, die Sie hier festlegen, überschreiben die Werte, die für das Farbschema definiert sind. Sie müssen eine Farbe auf den **Standard** Wert zurücksetzen, wenn Sie Sie geändert haben, aber die Standardfarben für das Farbschema verwenden möchten.

## <a name="customize-the-toolbars"></a>Anpassen der Symbolleisten

Die Symbolleisten stellen eine bequeme Möglichkeit dar, Befehle mit einem einzigen Mausklick auszugeben, anstatt die Menüs oder Tastenkombinationen zu verwenden. Visual Studio enthält einen Standardsatz von Symbolleisten. Bei der C++ Standardentwicklung sind die nützlichsten Symbolleisten wahrscheinlich Standard, Text-Editor, Build, Debug, Quell Code Verwaltung und Dateien, die möglicherweise verglichen werden. Bei der Windows-Entwicklung sind der Dialog-Editor und der Bild-Editor nützlich zum Anordnen von Dialogfeldern und zum Bearbeiten von Symbolen.

Zeigen Sie auf die Symbole auf der Symbolleiste, um den Befehl anzuzeigen, den Sie darstellt:

![Symbolleisten-QuickInfo](media/toolbar-mouse-hover.png)

Sie können Befehle hinzufügen oder entfernen oder eine benutzerdefinierte Symbolleiste erstellen, indem Sie auf den Pfeil nach unten klicken. Um die Symbolleiste an einen neuen Speicherort zu verschieben, ziehen Sie Sie in der gepunkteten Leiste auf der linken Seite:

![Anpassen oder Verschieben einer Symbolleiste](media/toolbar-move-edit.png).

Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Menüs und Symbolleisten in Visual Studio @ no__t-0.

## <a name="show-or-hide-line-numbers"></a>Anzeigen oder Ausblenden von Zeilennummern

Um anzugeben, ob die Zeilennummern auf der linken Seite des Editor-Fenster angezeigt werden, navigieren Sie zu, und aktivieren oder deaktivieren Sie die **Zeilennummern**:

![Zeilennummern](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>Erstellen von Tastenkombinationen

Alle Befehle in Visual Studio können mithilfe von Tastenkombinationen mithilfe verschiedener Tastenkombinationen mit der Tastenkombination STRG, alt und UMSCHALT erstellt werden. Sie können Ihre eigenen Verknüpfungen **erstellen, indem Sie zu**Extras  > **Optionen** > **Umgebung** > -**Tastatur** navigieren (oder **STRG + Q** eingeben und nach "Verknüpfungen" suchen). Weitere Informationen finden Sie unter [identifizieren und Anpassen von Tastenkombinationen in Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).
