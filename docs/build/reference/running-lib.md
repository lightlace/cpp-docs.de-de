---
title: "Ausf&#252;hren von LIB"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.TargetMachine"
  - "Lib"
  - "VC.Project.VCLibrarianTool.PrintProgress"
  - "VC.Project.VCLibrarianTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ (Befehlsdateien)"
  - "/MACHINE (Zielplattformoption)"
  - "/NOLOGO (Bibliotheks-Manager-Option)"
  - "/VERBOSE (Bibliotheks-Manager-Option)"
  - "Doppelpunkt in Befehlsdateien"
  - "Befehlsdateien"
  - "Befehlsdateien, LIB"
  - "Bindestrich-Optionsbezeichner"
  - "Schrägstrich-Optionsbezeichner"
  - "LIB [C++], Ausführen von LIB"
  - "MACHINE (Zielplattformoption)"
  - "-MACHINE (Zielplattformoption)"
  - "NOLOGO (Bibliotheks-Manager-Option)"
  - "-NOLOGO (Bibliotheks-Manager-Option)"
  - "Semikolon, Befehlsdateien"
  - "Schrägstrich (/)"
  - "VERBOSE (Bibliotheks-Manager-Option)"
  - "-VERBOSE (Bibliotheks-Manager-Option)"
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Ausf&#252;hren von LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zur Steuerung von LIB stehen Ihnen verschiedene Befehlszeilenoptionen zur Verfügung.  
  
## LIB\-Befehlszeile  
 Um LIB auszuführen, geben Sie den Befehl `lib` sowie die Optionen und Dateinamen für die Task an, die von LIB ausgeführt werden sollen.  LIB kann auch zur Eingabe von Befehlszeilen über Befehlsdateien verwendet werden, die im folgenden Abschnitt beschrieben werden.  LIB verwendet keine Umgebungsvariable.  
  
> [!NOTE]
>  Wenn Sie Erfahrung mit den Tools LINK32.EXE und LIB32.EXE haben, die zum Win32\-SDK \(Software Development Kit\) für Microsoft Windows NT gehören, haben Sie möglicherweise schon die Befehle `link32 -lib` oder `lib32` verwendet, um Bibliotheken zu verwalten und Importbibliotheken zu erstellen.  Stellen Sie sicher, dass Ihre Makefiles und Batchdateien stattdessen den Befehl `lib` verwenden.  
  
## LIB\-Befehlsdateien  
 Sie können Befehlszeilenargumente in einer Befehlsdatei an LIB übergeben, indem Sie die folgende Syntax verwenden:  
  
```  
LIB @commandfile  
```  
  
 Die Datei `commandfile` ist eine Textdatei.  Zwischen dem @\-Zeichen und dem Dateinamen sind keine Leerzeichen oder Tabstopps zulässig.  Da es keine Standard\-Dateinamenerweiterung gibt, müssen Sie den vollen Dateinamen inklusive Erweiterungen angeben.  Platzhalter können nicht verwendet werden.  Sie können mit dem Dateinamen einen absoluten oder relativen Pfad angeben.  
  
 In der Befehlsdatei können Argumente genauso wie in der Befehlszeile durch Leerzeichen oder Tabstopps voneinander getrennt werden; sie können auch durch Zeilenumbruchzeichen getrennt werden.  Verwenden Sie ein Semikolon \(;\), um den Beginn eines Kommentars zu markieren.  LIB ignoriert den gesamten Text vom Semikolon bis zum Zeilenende.  
  
 Die Befehlszeile kann entweder vollständig oder teilweise in einer Befehlsdatei angegeben werden, und es können auch mehrere Befehlsdateien in einem LIB\-Befehl verwendet werden.  LIB behandelt die Eingabe über die Befehlsdatei genauso wie eine Eingabe an der betreffenden Stelle in der Befehlszeile.  Befehlsdateien können nicht geschachtelt werden.  LIB zeigt den Inhalt von Befehlsdateien auf dem Bildschirm an, sofern nicht die **\/NOLOGO**\-Option verwendet wird.  
  
## Verwenden der LIB\-Optionen  
 Eine Option besteht aus einem Optionsbezeichner, entweder einem Bindestrich \(–\) oder einem Schrägstrich \(\/\), sowie dem darauf folgenden Optionsnamen.  Optionsnamen können nicht abgekürzt werden.  Einige Optionen verfügen über Argumente, die nach einem Doppelpunkt \(:\) angegeben werden.  Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig.  Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen.  Bei Optionsnamen und ihren aus Schlüsselwörtern oder Dateinamen bestehenden Argumenten wird keine Groß\-\/Kleinschreibung berücksichtigt. Bei Bezeichnern, die als Argumente verwendet werden, wird sie hingegen beachtet.  LIB verarbeitet Optionen in der Reihenfolge, in der sie in der Befehlszeile oder in Befehlsdateien angegeben sind.  Wenn eine Option mit verschiedenen Argumenten wiederholt wird, dann hat die zuletzt genannte Vorrang.  
  
 Die folgenden Optionen können in allen LIB\-Modi angewendet werden:  
  
 \/ERRORREPORT \[NONE &#124; PROMPT &#124; QUEUE &#124; SEND\]  
 Wenn die Ausführung von lib.exe zur Laufzeit fehlschlägt, können mit \/ERRORREPORT Informationen über diese internen Fehler an Microsoft gesendet werden.  
  
 Weitere Informationen über \/ERRORREPORT finden Sie unter [\/errorReport \(Meldung über interne Compilerfehler\)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 \/LTCG  
 Bewirkt, dass die Bibliothek mit Link\-Zeitcodegenerierung generiert wird.  Weitere Informationen finden Sie unter [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 \/MACHINE  
 Gibt die Zielplattform für das Programm an.  Normalerweise brauchen Sie diese Option nicht anzugeben.  LIB leitet den Computertyp aus den OBJ\-Dateien ab.  Unter Umständen kann LIB jedoch den Computertyp nicht bestimmen und gibt eine Fehlermeldung aus.  Geben Sie "\/MACHINE" an, wenn ein solcher Fehler auftritt.  Im **\/EXTRACT**\-Modus wird diese Option nur zur Überprüfung verwendet.  Geben Sie in der Befehlszeile `lib /?` ein, um die verfügbaren Computertypen anzuzeigen.  
  
 \/NOLOGO  
 Unterdrückt die Anzeige der Copyrightmeldung und der Versionsnummer von LIB und verhindert die Anzeige von Befehlsdateien.  
  
 \/VERBOSE  
 Zeigt Details über den Fortschritt der Sitzung an, einschließlich Namen der OBJ\-Dateien, die hinzugefügt werden.  Diese Informationen werden an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.  
  
 \/WX\[:NO\]  
 Behandelt Warnungen als Fehler.  Weitere Informationen finden Sie unter [\/WX \(Linkerwarnungen als Fehler behandeln\)](../../build/reference/wx-treat-linker-warnings-as-errors.md).  
  
 Andere Optionen sind nur für spezifische LIB\-Modi zulässig.  Sie werden in den Abschnitten behandelt, in denen die einzelnen Modi beschrieben sind.  
  
## Siehe auch  
 [LIB\-Referenz](../../build/reference/lib-reference.md)