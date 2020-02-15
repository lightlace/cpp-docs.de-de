---
title: BSCMAKE-Optionen
description: Verweis auf die Befehlszeilenoptionen des Microsoft BSCMAKE-Hilfsprogramms.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
ms.openlocfilehash: f0fd0e01d3325267ac175435aab65b5d0a9d47ea
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257792"
---
# <a name="bscmake-options"></a>BSCMAKE-Optionen

> [!WARNING]
> Obwohl BSCMAKE weiterhin mit Visual Studio installiert wird, wird es nicht mehr von der IDE verwendet. Seit Visual Studio 2008 werden durchsuchen und Symbol Informationen automatisch in einer SQL Server *`.sdf`* -Datei im Projektmappenordner gespeichert.

In diesem Abschnitt werden die Optionen beschrieben, die zur Steuerung von BSCMAKE zur Verfügung stehen. Der Inhalt der Browserinformationsdatei lässt sich durch Ausschließen oder Einschließen bestimmter Informationen mithilfe verschiedener Optionen steuern. Durch die Ausschluss Optionen kann BSCMAKE schneller ausgeführt werden, und es kann zu einer kleineren *`.bsc`* Datei führen. Bei Optionsnamen wird die Groß-/Kleinschreibung beachtet (mit Ausnahme von **/Help** und **/nologo**).

Nur **/nologo** und **/o** sind in der Visual Studio-Entwicklungsumgebung verfügbar.  Informationen zum Zugriff auf die Eigenschaften Seiten eines Projekts finden Sie [unter C++ Festlegen von Compiler-und Buildeigenschaften in Visual Studio](../working-with-project-properties.md) .

**/Ei (** _Dateiname_... **)** \
Schließt den Inhalt der angegebenen Includedateien aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden. Wenn Sie nur einen *Dateinamen*angeben, sind keine Klammern erforderlich. Verwenden Sie **/Ei** zusammen mit der Option **/es** , um Dateien auszuschließen, die nicht von **/es**ausgeschlossen wurden.

**/El**\
Schließt lokale Symbole aus. Standardmäßig werden lokale Symbole eingeschlossen. Weitere Informationen zu lokalen Symbolen finden Sie unter [Erstellen einer SBR-Datei](creating-an-dot-sbr-file.md).

**/EM**\
Schließt Symbole in Makros aus. Verwenden Sie **/EM** , um nur die Namen von Makros in die Browseinformationsdatei einzuschließen. Standardmäßig werden Makronamen und das Ergebnis der Makroerweiterungen eingeschlossen.

**/Er (** _Symbol_... **)** \
Schließt die angegebenen Symbole aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Symbolnamen müssen diese durch ein Leerzeichen getrennt und die Liste in runde Klammern eingeschlossen werden. Klammern sind nicht erforderlich, wenn Sie nur ein *Symbol*angeben.

**/Es**\
Schließt jede mit einem absoluten Pfad angegebene Includedatei aus oder befindet sich in einem absoluten Pfad, der in der INCLUDE-Umgebungsvariablen angegeben ist. (In der Regel handelt es sich bei diesen Dateien um Dateien im System, die viele Informationen enthalten, die Sie möglicherweise nicht in der Browseinformationsdatei benötigen.) Mit dieser Option werden keine Dateien ausgeschlossen, die ohne Pfad angegeben sind, oder mit relativen Pfaden oder Dateien, die in einem relativen Pfad in enthalten sind. Sie können die **/Ei** -Option zusammen mit **/es** verwenden, um Dateien auszuschließen, die nicht von **/es** ausgeschlossen werden. Wenn Sie nur einige der Dateien ausschließen möchten, verwenden Sie **/Ei** anstelle von **/es**, und Listen Sie die Dateien auf, die Sie ausschließen möchten.

**/errorreport:** [**None** &#124; **prompt** &#124; **Queue** &#124; **Send**] \
Diese Option ist veraltet. Ab Windows Vista wird die Fehlerberichterstattung durch [Windows-Fehlerberichterstattung (wer)](/windows/win32/wer/windows-error-reporting) -Einstellungen gesteuert.

**/Help**\
Zeigt eine Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.

**/IU**\
Schließt Symbole ein, auf die nicht verwiesen wird. Standardmäßig zeichnet BSCMAKE keine Symbole auf, die definiert sind, auf die jedoch nicht verwiesen wird. Wenn eine *`.sbr`* Datei gepackt wurde, hat diese Option keine Auswirkung auf diese Eingabedatei, da der Compiler die Symbole, auf die nicht verwiesen wird, bereits entfernt hat.

**/n**\
Erzwingt ein nicht inkrementelles Erstellen. Verwenden Sie **/n** , um einen vollständigen Build der Browseinformationen zu erzwingen, ob eine *`.bsc`* Datei vorhanden ist oder nicht, und um zu verhindern, dass *`.sbr`* Dateien abgeschnitten werden. Erfahren Sie, [wie BSCMAKE eine BSC-Datei erstellt](how-bscmake-builds-a-dot-bsc-file.md).

**/Nologo**\
Unterdrückt die Copyrightmeldung von BSCMAKE.

**/o** *filename* -\
Gibt einen Namen für die Browserinformationsdatei an. Standardmäßig gibt BSCMAKE die Browseinformationsdatei als Basis Namen für die erste *`.sbr`* Datei und eine *`.bsc`* Erweiterung an.

**/S (** _Dateiname_... **)** \
Weist BSCMAKE an, die angegebene Includedatei beim ersten Auftreten zu verarbeiten und andernfalls auszuschließen. Verwenden Sie diese Option, um Verarbeitungszeit zu sparen, wenn eine Datei (z. b. eine Kopfzeile oder eine *`.h`* Datei für eine *`.c`* oder eine *`.cpp`* Quelldatei) in mehreren Quelldateien enthalten ist, aber nicht jedes Mal durch Vorverarbeitungs Direktiven unverändert bleibt. Verwenden Sie diese Option, wenn eine Datei in der von Ihnen erstellten Datei zum Durchsuchen von Informationen nicht unwichtig geändert wird. Wenn Sie mehrere Dateien angeben möchten, trennen Sie die Namen durch ein Leerzeichen, und schließen Sie die Liste in Klammern ein. Wenn Sie nur einen *Dateinamen*angeben, sind keine Klammern erforderlich. Wenn Sie die Datei bei jedem einschließen ausschließen möchten, verwenden Sie die Option **/Ei** oder **/es** .

**/v**\
Stellt eine ausführliche Ausgabe bereit, die den Namen der einzelnen *`.sbr`* verarbeiteten Dateien sowie Informationen über die gesamte BSCMAKE-Ausführung enthält.

**/?** \
Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.

Die folgende Befehlszeile teilt BSCMAKE mit, dass aus drei *`.sbr`* Dateien ein vollständiger Build von Main. BSC durchzuführen ist. Dabei sollen doppelte Instanzen von TOOLBOX.H ausgeschlossen werden:

```cmd
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>Weitere Informationen

[BSCMAKE-Referenz](bscmake-reference.md)
