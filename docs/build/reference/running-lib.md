---
title: Ausführen von LIB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c306ba58bfef11f92d7e861272aad2aa605c8fde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="running-lib"></a>Ausführen von LIB
Verschiedener Befehlszeilenoptionen können zur Steuerung von LIB verwendet werden.  
  
## <a name="lib-command-line"></a>LIB-Befehlszeile  
 Geben Sie den Befehl zum Ausführen von LIB `lib` gefolgt von den Optionen und Dateinamen für die Aufgabe sind Sie LIB ausführen verwenden. LIB akzeptiert auch Befehlszeileneingabe in Befehlsdateien, die im folgenden Abschnitt beschrieben werden. Eine Umgebungsvariable verwendet LIB nicht.  
  
> [!NOTE]
>  Wenn Sie mit der LINK32.exe vertraut sind und mit der Microsoft Win32-Software Development Kit für Windows NT, Sie entweder den Befehl verwendet haben möglicherweise tools LIB32.exe `link32 -lib` oder den Befehl `lib32` zum Erstellen und Verwalten von Bibliotheken Importbibliotheken. Achten Sie darauf, dass Sie so ändern Sie die Makefiles und Batch-Dateien mit der `lib` stattdessen den Befehl.  
  
## <a name="lib-command-files"></a>LIB-Befehlsdateien  
 Sie können Befehlszeilenargumente an LIB in eine Befehlsdatei mithilfe der folgenden Syntax übergeben:  
  
```  
LIB @commandfile  
```  
  
 Die Datei `commandfile` ist eine Textdatei. Keine Leerzeichen oder Tabstopp ist zulässig, zwischen dem at-Zeichen (@) und den Dateinamen. Es ist keine standarderweiterung. Sie müssen den vollständigen Dateinamen, einschließlich Erweiterung angeben. Keine werden Platzhalter verwendet. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben.  
  
 In der Befehlsdatei können Argumente durch Leerzeichen oder Tabstopps getrennt werden, wie sie in der Befehlszeile können; Sie können auch durch Zeilenumbruchzeichen getrennt werden. Verwenden Sie ein Semikolon (;), um einen Kommentar zu kennzeichnen. LIB ignoriert den gesamten Text vom Semikolon am Ende der Zeile.  
  
 Sie können entweder vollständig oder teilweise von der Befehlszeile angeben, in einer Befehlsdatei und können Sie mehr als eine Befehlsdatei in einer LIB-Befehl. LIB akzeptiert die Befehlsdatei Eingabe, als ob er an der entsprechenden Position in der Befehlszeile angegeben wurden. Befehlsdateien können nicht geschachtelt werden. LIB wiederholt den Inhalt von Befehlsdateien, es sei denn, die/nologo-Option verwendet wird.  
  
## <a name="using-lib-options"></a>Verwenden die LIB-Optionen  
 Eine Option besteht aus einem Optionsbezeichner, entweder einem Bindestrich (-) oder einem Schrägstrich (/), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben ein Argument an, nach einem Doppelpunkt (:)) angegeben. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Optionsnamen und ihren aus Schlüsselwörtern oder Dateinamen bestehenden Argumenten werden nicht Groß-/Kleinschreibung beachtet, aber Bezeichner, die als Argumente verwendet Groß-/Kleinschreibung beachtet. LIB verarbeitet Optionen in der Reihenfolge, in der Befehlszeile angegeben und in Befehlsdateien. Wenn eine Option mit anderen Argumenten wiederholt wird, hat das letzte Lesezeichen zu verarbeitenden Vorrang vor.  
  
 Die folgenden Optionen gelten für alle Modi lib:  
  
 / ERRORREPORT [NONE &AMP;#124; PROMPT &AMP;#124; WARTESCHLANGE &AMP;#124; SENDEN]  
 Wenn lib.exe zur Laufzeit fehlschlägt, können Sie die/errorreport verwenden, um Informationen über diese internen Fehler an Microsoft gesendet.  
  
 Weitere Informationen zu/errorreport, finden Sie unter [/errorreport (Bericht interne Compilerfehler)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 /LTCG  
 Bewirkt, dass die Bibliothek mit Link-zeitcodegenerierung erstellt werden sollen.  Weitere Informationen finden Sie unter [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 /MACHINE  
 Gibt die Zielplattform für das Programm an. In der Regel müssen Sie nicht "/ Machine" angeben. LIB leitet den Computertyp aus den OBJ-Dateien ab. Allerdings wird unter Umständen ein LIB den Computertyp kann nicht bestimmt werden kann und eine Fehlermeldung ausgegeben. Geben Sie "/MACHINE" an, wenn ein solcher Fehler auftritt. Im Modus Memberobjekt ist diese Option nur zur Überprüfung. Verwendung `lib /?` in der Befehlszeile verfügbare Maschine Typen anzuzeigen.  
  
 /NOLOGO  
 Unterdrückt die Anzeige von der Anzahl der copyright LIB-Nachricht und Version, und verhindert die Anzeige von Befehlsdateien.  
  
 /VERBOSE  
 Zeigt Details zu den Status der Sitzung, einschließlich Namen, der die OBJ-Dateien, die hinzugefügt wird. Die Informationen werden an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.  
  
 / WX [: NO]  
 Behandeln Sie Warnungen als Fehler. Finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](../../build/reference/wx-treat-linker-warnings-as-errors.md) für Weitere Informationen.  
  
 Andere Optionen gelten nur für bestimmte LIB-Modi. Diese Optionen werden in den Abschnitten beschreiben die einzelnen Modi erläutert.  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)