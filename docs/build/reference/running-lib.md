---
title: Ausführen von LIB
ms.date: 09/28/2018
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
ms.openlocfilehash: 73a259faa57d74fbe535bfa329dfc2a39cb6bbad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656975"
---
# <a name="running-lib"></a>Ausführen von LIB

Zur Steuerung von LIB können verschiedene Befehlszeilenoptionen verwendet werden.

## <a name="lib-command-line"></a>LIB-Befehlszeile

Geben Sie den Befehl zum Ausführen von LIB `lib` gefolgt von der Optionen und Dateinamen für die Aufgabe Sie mithilfe der LIB ausführen. LIB akzeptiert auch Befehlszeileneingaben in Befehlsdateien, die im folgenden Abschnitt beschrieben werden. Eine Umgebungsvariable verwendet LIB nicht.

> [!NOTE]
> Wenn Sie gewohnt, die LINK32.exe sind und tools mit der Microsoft Win32-Software Development Kit für Windows NT, Sie den Befehl verwendet haben möglicherweise LIB32.exe `link32 -lib` oder mit dem Befehl `lib32` zum Erstellen und Verwalten von Bibliotheken Importieren Sie die Bibliotheken. Achten Sie darauf, dass Sie so ändern Sie Ihre Makefiles und Batch-Dateien mit der `lib` stattdessen den Befehl.

## <a name="lib-command-files"></a>LIB-Befehlsdateien

Sie können Befehlszeilenargumente an LIB in einer Befehlsdatei, die mit der folgenden Syntax übergeben:

> **LIB \@**  <em>Commandfile</em>

Die Datei *Commandfile* ist eine Textdatei. Keine Leerzeichen oder Tabstopp kann zwischen den at-Zeichen (**\@**) und den Dateinamen. Es gibt keine standardmäßige Erweiterung. Sie müssen den vollständigen Namen, Einbinden von Erweiterungen angeben. Platzhalter können verwendet werden. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben.

In der Befehlsdatei können Argumente durch Leerzeichen oder Tabulatorzeichen, getrennt werden, wie sie in der Befehlszeile können; Sie können auch durch Zeilenumbruchzeichen getrennt werden. Verwenden Sie ein Semikolon (**;**) um einen Kommentar zu markieren. LIB ignoriert den gesamten Text aus dem Semikolon am Ende der Zeile.

Sie können entweder vollständig oder teilweise von der Befehlszeile angeben, in einer Befehlsdatei aus, und Sie können mehr als eine Befehlsdatei in eine LIB-Befehl verwenden. LIB akzeptiert die Befehlsdatei-Eingaben, als ob es an diesem Speicherort in der Befehlszeile angegeben wurden. Befehlsdateien werden nicht geschachtelt. LIB gibt den Inhalt der Befehlsdateien, es sei denn, die/nologo-Option verwendet wird.

## <a name="using-lib-options"></a>Verwenden die LIB-Optionen

Eine Option besteht aus einem Optionsbezeichner, handelt es sich entweder einem Bindestrich (**-**) oder einem Schrägstrich (**/**), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben ein Argument, das nach einem Doppelpunkt angegeben (**:**). Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Optionsnamen und ihren Schlüsselwörtern oder Dateinamen bestehenden Argumenten sind nicht Groß-/Kleinschreibung beachtet, aber Bezeichner, die als Argumente verwendet werden Groß-/Kleinschreibung beachtet. LIB verarbeitet die Optionen in der Reihenfolge, in der Befehlszeile angegeben und in Befehlsdateien. Wenn Sie eine Option mit verschiedenen Argumenten wiederholt wird, hat der letzte Suchvorgang zu verarbeitenden Vorrang vor.

Die folgenden Optionen gelten für alle LIB-Modi:

> **/ ERRORREPORT** [**NONE** &AMP;#124; **EINGABEAUFFORDERUNG** &AMP;#124; **WARTESCHLANGE** &AMP;#124; **SENDEN**]

Wenn lib.exe zur Laufzeit ein Fehler auftritt, können Sie **/errorreport** Informationen zu diesen internen Fehlern an Microsoft zu senden.

Weitere Informationen zu **/errorreport**, finden Sie unter [/errorreport (interne Compilerfehler Bericht)](../../build/reference/errorreport-report-internal-compiler-errors.md).

> **/LTCG**

"LTCG" steht für *Link-zeitcodegenerierung*. Dieses Feature erfordert die Zusammenarbeit zwischen den Compiler ([cl.exe](compiler-options.md)), LIB und der Linker ([LINK](linker-options.md)) um die Code über eine beliebige Komponente selbst Möglichkeiten zu optimieren.

Für LIB die **"/ LTCG"** Option gibt an, dass die Eingaben von cl.exe Objektdateien, die mithilfe von generiert wurden die ["/ GL"](gl-whole-program-optimization.md) -Compileroption. Wenn LIB derartige Eingaben auftreten und **"/ LTCG"** nicht angegeben ist, er wird neu gestartet, mit "/ LTCG" aktiviert, nachdem die Meldung dient zu Informationszwecken angezeigt. Das heißt, es ist nicht erforderlich, diese Option explizit festzulegen, aber beschleunigt Buildleistung, da LIB nicht unbedingt selbst neu.

Im Buildprozess wird die Ausgabe von LIB Link gesendet. LINK verfügt über einen eigenen separaten **"/ LTCG"** Option aus, die zum Ausführen von verschiedenen Optimierungen, einschließlich der Optimierung des ganzen Programms und Profilgesteuerte Optimierung (PGO)-Instrumentation verwendet wird. Weitere Informationen über die LINK-Option finden Sie unter ["/ LTCG"](ltcg-link-time-code-generation.md).

> **/MACHINE**

Gibt die Zielplattform für das Programm an. In der Regel müssen Sie nicht/Machine angeben. LIB leitet den Computertyp aus den OBJ-Dateien ab. Allerdings wird in einigen Fällen ein LIB den Computertyp kann nicht bestimmt werden kann und eine Fehlermeldung ausgegeben. Geben Sie "/MACHINE" an, wenn ein solcher Fehler auftritt. Im/EXTRACT-Modus wird diese Option nur zur Überprüfung. Verwendung `lib /?` in der Befehlszeile, um die verfügbaren Computertypen finden Sie unter.

> **/NOLOGO**

Unterdrückt die Anzeige der LIB Copyrightmeldung und der Versionsnummer, und verhindert die Anzeige von Befehlsdateien aus.

> **/VERBOSE**

Zeigt Details zu den Status der Sitzung, einschließlich Namen OBJ-Dateien hinzugefügt wird. Die Informationen werden an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.

> **/ WX**[**: NO**]

Behandeln Sie Warnungen als Fehler. Finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](../../build/reference/wx-treat-linker-warnings-as-errors.md) für Weitere Informationen.

Andere Optionen gelten nur für bestimmte LIB-Modi. Diese Optionen werden in den Abschnitten, die Beschreibung der einzelnen Modi erläutert.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)
