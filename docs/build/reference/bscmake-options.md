---
title: BSCMAKE-Optionen
ms.date: 11/04/2016
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
ms.openlocfilehash: 7727f433ae68f26075645b35ff5edad43159ec67
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415408"
---
# <a name="bscmake-options"></a>BSCMAKE-Optionen

In diesem Abschnitt werden die Optionen beschrieben, die zur Steuerung von BSCMAKE zur Verfügung stehen. Der Inhalt der Browserinformationsdatei lässt sich durch Ausschließen oder Einschließen bestimmter Informationen mithilfe verschiedener Optionen steuern. Die Ausschlussoptionen ermöglichen eine schnellere Ausführung von BSCMAKE und können eine kleinere BSC-Datei zur Folge haben. Optionsnamen Groß-/Kleinschreibung (mit Ausnahme von **/HELP** und **/nologo**).

Nur **/nologo** und **/o** stehen in der Visual Studio-Entwicklungsumgebung.  Finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md) Zugriff auf Informationen zu Eigenschaftenseiten des Projekts.

**/Ei (** *filename*...**)**<br/>
Schließt den Inhalt der angegebenen Includedateien aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden. Klammern sind nicht erforderlich, wenn Sie nur einen angeben *Filename*. Verwendung **Ei** zusammen mit den **/es einsetzen** Option zum Ausschließen von Dateien, die nicht von ausgeschlossen **/es einsetzen**.

**/El**<br/>
Schließt lokale Symbole aus. Standardmäßig werden lokale Symbole eingeschlossen. Weitere Informationen über lokale Symbole finden Sie unter [Erstellen einer SBR-Datei](../../build/reference/creating-an-dot-sbr-file.md).

**/Em**<br/>
Schließt Symbole in Makros aus. Verwendung **/em** um nur die Namen von Makros in der Browserinformationsdatei einzuschließen. Standardmäßig werden Makronamen und das Ergebnis der Makroerweiterungen eingeschlossen.

**/Er (** *Symbol*... **)**<br/>
Schließt die angegebenen Symbole aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Symbolnamen müssen diese durch ein Leerzeichen getrennt und die Liste in runde Klammern eingeschlossen werden. Klammern sind nicht erforderlich, wenn Sie nur einen angeben *Symbol*.

**/Es**<br/>
Schließt die Includedateien, die mit einem absoluten Pfad angegeben oder in einem absoluten Pfad gefunden werden, der in der INCLUDE-Umgebungsvariablen angegeben ist, aus der Browserinformationsdatei aus. (Gewöhnlich sind dies die Includedateien des Systems, die viele Informationen enthalten, die in der Browserinformationsdatei möglicherweise nicht benötigt werden.) Diese Option schließt keine Dateien aus, die ohne Pfad oder mit einem relativen Pfad angegeben sind oder in einem relativen Pfad in INCLUDE gefunden werden. Sie können die **Ei** -Option zusammen mit **/es einsetzen** um Dateien auszuschließen, **/es einsetzen** nicht ausgeschlossen. Wenn Sie nur einige der Dateien ausschließen möchten, die **/es einsetzen** ausschließt, verwenden Sie **Ei** anstelle von **/es einsetzen** und Auflisten der Dateien, die Sie ausschließen möchten.

**/errorreport:**[**none** &#124; **prompt** &#124; **queue** &#124; **send**]<br/>
Ermöglicht das Senden von Informationen in Bezug auf interne Fehler in bscmake.exe an Microsoft.

Weitere Informationen zu **/errorreport**, finden Sie unter [/errorreport (interne Compilerfehler Bericht)](../../build/reference/errorreport-report-internal-compiler-errors.md).

**/HELP**<br/>
Zeigt eine Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.

**/Iu**<br/>
Schließt Symbole ein, auf die nicht verwiesen wird. Standardmäßig zeichnet BSCMAKE keine Symbole auf, die zwar definiert sind, auf die aber nicht verwiesen wird. Wenn eine SBR-Datei komprimiert wurde, hat diese Option für diese Eingabedatei keine Auswirkungen, da der Compiler bereits die Symbole entfernt hat, auf die nicht verwiesen wird.

**/n**<br/>
Erzwingt ein nicht inkrementelles Erstellen. Verwendung **/n** um eine vollständige Erstellung der Browserinformationsdatei zu erzwingen, und zwar unabhängig davon, ob eine BSC-Datei vorhanden ist, und um zu verhindern, dass SBR-Dateien abgeschnitten wird. Finden Sie unter [wie eine BSC-Datei mit BSCMAKE](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md).

**/NOLOGO**<br/>
Unterdrückt die Copyrightmeldung von BSCMAKE.

**/ o** *Dateiname*<br/>
Gibt einen Namen für die Browserinformationsdatei an. Standardmäßig gibt BSCMAKE der Browserinformationsdatei den Basisnamen der ersten SBR-Datei mit der Erweiterung BSC.

**/ S (** *Filename*... **)**<br/>
Weist BSCMAKE an, die angegebene Includedatei bei deren ersten Auftreten zu verarbeiten und ansonsten auszuschließen. Mit dieser Option kann Verarbeitungszeit eingespart werden, wenn eine Datei, beispielsweise eine Headerdatei (.h-Datei) für eine C- oder CPP-Quelldatei, in verschiedene Quelldateien miteinbezogen, aber jeweils nicht von Präprozessoranweisungen geändert wird. Diese Option kann auch verwendet werden, wenn die Änderungen an einer Datei für die zu erstellende Browserinformationsdatei nicht relevant sind. Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden. Klammern sind nicht erforderlich, wenn Sie nur einen angeben *Filename*. Wenn Sie verwenden möchten, schließen Sie die Datei jedes Mal, wenn sie eingeschlossen wird, verwenden Sie die **Ei** oder **/es einsetzen** Option.

**/v**<br/>
Erzeugt eine ausführliche Ausgabe, die den Namen jeder verarbeiteten SBR-Datei sowie Informationen über die gesamte BSCMAKE-Ausführung einschließt.

**/?**<br/>
Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.

Mit der nachfolgenden Befehlszeile wird BSCMAKE veranlasst, eine vollständige Erstellung der Datei "MAIN.bsc" anhand von drei SBR-Dateien durchzuführen. Dabei sollen doppelte Instanzen von TOOLBOX.H ausgeschlossen werden:

```
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>Siehe auch

[BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)
