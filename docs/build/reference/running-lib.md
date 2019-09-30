---
title: Ausführen von LIB
description: Beschreibt die Befehlszeilenoptionen, die Sie mit "lib. exe" verwenden können.
ms.date: 09/25/2019
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
ms.openlocfilehash: 0d65c8d8b3b0cd28c7cccda25bfd9512321172f9
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685541"
---
# <a name="running-lib"></a>Ausführen von LIB

Zum Steuern von lib können verschiedene Befehlszeilenoptionen verwendet werden.

## <a name="lib-command-line"></a>LIB-Befehlszeile

Um lib auszuführen, geben Sie den Befehl `lib` gefolgt von den Optionen und Dateinamen für die Aufgabe ein, die Sie für die Ausführung von lib verwenden. LIB akzeptiert auch Befehlszeilen Eingaben in Befehls Dateien, die im folgenden Abschnitt beschrieben werden. LIB verwendet keine Umgebungsvariable.

## <a name="lib-command-files"></a>LIB-Befehls Dateien

Sie können Befehlszeilenargumente an lib in einer Befehlsdatei übergeben, indem Sie die folgende Syntax verwenden:

> **Lib-\@-** <em>Befehlsdatei</em>

Die Datei *Befehlsdatei* ist eine Textdatei. Zwischen dem @-Zeichen ( **\@** ) und dem Dateinamen sind keine Leerzeichen oder Tabstopps zulässig. Der Name der *Befehlsdatei* hat keine Standard Erweiterung. Sie müssen den vollständigen Dateinamen angeben, einschließlich einer beliebigen Erweiterung. Platzhalter können nicht verwendet werden. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben.

In der Befehlsdatei können Argumente durch Leerzeichen oder Tabstopps getrennt werden, wie Sie in der Befehlszeile angezeigt werden können. Argumente können auch durch Zeilen vorzeichenzeichen getrennt werden. Verwenden Sie ein Semikolon ( **;** ), um einen Kommentar zu markieren. LIB ignoriert den gesamten Text vom Semikolon bis zum Ende der Zeile.

Sie können entweder die gesamte Befehlszeile oder einen Teil der Befehlszeile in einer Befehlsdatei angeben, und Sie können mehr als eine Befehlsdatei in einem LIB-Befehl verwenden. LIB akzeptiert die Befehlsdatei Eingabe so, als ob Sie an dieser Stelle in der Befehlszeile angegeben wird. Befehls Dateien können nicht eingefügt werden. LIB gibt den Inhalt von Befehls Dateien an, es sei denn, die Option **/nologo** wird verwendet.

## <a name="using-lib-options"></a>Verwenden von lib-Optionen

Eine Option besteht aus einem optionsspezifizierer, bei dem es sich entweder um einen Bindestrich ( **-** ) oder um einen Schrägstrich ( **/** ) handelt, gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen akzeptieren ein Argument, das nach einem Doppelpunkt ( **:** ) angegeben wird. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Bei Optionsnamen und Schlüsselwörtern oder Dateinamen Argumenten wird die Groß-/Kleinschreibung nicht beachtet LIB verarbeitet Optionen in der Reihenfolge, die in der Befehlszeile und in den Befehls Dateien angegeben ist. Wenn eine Option mit unterschiedlichen Argumenten wiederholt wird, hat die letzte zu verarbeitende Priorität Vorrang.

Die folgenden Optionen gelten für alle Modi von lib:

> **/ERRORREPORT** \[**KEINE** &#124; **PROMPT** &#124; - **WARTESCHLANGE** &#124; **SENDEN**]

Wenn lib. exe zur Laufzeit fehlschlägt, können Sie **/errorreport** verwenden, um Informationen zu diesen internen Fehlern an Microsoft zu senden.

Weitere Informationen zu **/errorreport**finden Sie unter [/errorreport (interne Compilerfehler melden)](errorreport-report-internal-compiler-errors.md).

> **/LINKREPRO:** _Verzeichnispfad_ \
> **/LINKREPROTARGET:** _Dateiname_

Sie können die [/LINKREPRO](linkrepro.md) -Option verwenden, um Microsoft bei der Diagnose von lib. exe-abstürzen und internen Fehlern zu unterstützen. Es generiert eine Verknüpfungs *Reproduktion, eine*Gruppe von buildartefakte, die Microsoft das reproduzieren eines Problems ermöglichen, das bei Bibliotheks Vorgängen auftritt. Die [/LINKREPROTARGET](linkreprotarget.md) -Option kann mit der **/LINKREPRO** -Option verwendet werden. Es werden nur Verknüpfungs Reproduktions Artefakte generiert, wenn "lib. exe" die angegebene Datei erzeugt. Weitere Informationen finden Sie unter [melden eines Problems mit dem Microsoft C++ -Toolset](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

> **/LTCG**

"LTCG" steht für die *Link-Zeit Codegenerierung*. Diese Funktion erfordert eine Zusammenarbeit zwischen dem Compiler ([cl. exe](compiler-options.md)), lib und dem Linker ([Link](linker-options.md)), um Code zu optimieren, der über die Funktionen von Komponenten hinausgeht.

Bei lib gibt die Option **/LTCG** an, dass die Eingaben aus cl. exe Objektdateien enthalten, die mit der [/GL](gl-whole-program-optimization.md) -Compileroption generiert wurden. Wenn lib solche Eingaben findet und **/LTCG** nicht angegeben ist, wird nach dem Anzeigen einer Informations Meldung mit/LTCG aktiviert. Anders ausgedrückt: Es ist nicht erforderlich, diese Option explizit festzulegen, aber die Buildleistung wird dadurch beschleunigt, da LIB nicht selbst neu gestartet werden muss.

Im Buildprozess wird die Ausgabe von lib an Link gesendet. Link hat eine eigene separate **/LTCG** -Option. Sie wird verwendet, um verschiedene Optimierungen auszuführen, einschließlich der Optimierung des gesamten Programms und der PGO-Instrumentation (Profil gesteuerte Optimierung). Weitere Informationen zur Link-Option finden Sie unter [/LTCG](ltcg-link-time-code-generation.md).

> **/MACHINE**

Gibt die Zielplattform für das Programm an. Normalerweise müssen Sie **/Machine**nicht angeben. LIB leitet den Computertyp aus den OBJ-Dateien ab. In einigen Fällen kann lib den Computertyp jedoch nicht ermitteln und eine Fehlermeldung ausgegeben. Wenn ein solcher Fehler auftritt, geben Sie **/Machine**an. Im **/extract** -Modus dient diese Option nur zur Überprüfung. Verwenden Sie `lib /?` an der Befehlszeile, um die verfügbaren Computertypen anzuzeigen.

> **/NOLOGO**

Unterdrückt die Anzeige der lib-Copyright Meldung und der Versionsnummer und verhindert das Wiederholen von Befehls Dateien.

> **/VERBOSE**

Zeigt Details zum Fortschritt der Sitzung an, einschließlich der Namen der OBJ-Dateien, die hinzugefügt werden. Die Informationen werden an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.

> **/WX**[ **:NO**]

Behandeln Sie Warnungen als Fehler. Weitere Informationen finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](wx-treat-linker-warnings-as-errors.md).

Andere Optionen gelten nur für bestimmte Modi von lib. Diese Optionen werden in den Abschnitten erläutert, in denen die einzelnen Modi beschrieben werden.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](lib-reference.md)
