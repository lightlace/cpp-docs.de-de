---
title: "BSCMAKE-Optionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCBscMakeTool.OutputFile"
  - "VC.Project.VCBscMakeTool.SuppressStartupBanner"
  - "VC.Project.VCBscMakeTool.PreserveSBR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/v (BSCMAKE-Option)"
  - "Iu (BSCMAKE-Option)"
  - "Browserinformationsdateien (.bsc), Inhalt"
  - "/Er (BSCMAKE-Option)"
  - "NOLOGO (BSCMAKE-Option)"
  - "/s (BSCMAKE-Option)"
  - "/Ei (BSCMAKE-Option)"
  - "/o (BSCMAKE-Option)"
  - "/NOLOGO (BSCMAKE-Option)"
  - "/Iu (BSCMAKE-Option)"
  - "s (BSCMAKE-Option /s)"
  - "/Em (BSCMAKE-Option)"
  - "Em (BSCMAKE-Option)"
  - "Es (BSCMAKE-Option)"
  - "Dateien [C++], BSCMAKE"
  - "Er (BSCMAKE-Option)"
  - "BSCMAKE, Optionen zum Steuern von Dateien"
  - "Steuern von BSCMAKE-Optionen"
  - "El (BSCMAKE-Option)"
  - "/El (BSCMAKE-Option)"
  - "/Es (BSCMAKE-Option)"
  - "Ei (BSCMAKE-Option)"
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# BSCMAKE-Optionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt werden die Optionen beschrieben, die zur Steuerung von BSCMAKE zur Verfügung stehen.  Der Inhalt der Browserinformationsdatei lässt sich durch Ausschließen oder Einschließen bestimmter Informationen mithilfe verschiedener Optionen steuern.  Die Ausschlussoptionen ermöglichen eine schnellere Ausführung von BSCMAKE und können eine kleinere BSC\-Datei zur Folge haben.  Bei den Optionsnamen \(außer **\/HELP** und **\/NOLOGO**\) ist die Schreibweise \(Groß\-\/Kleinschreibung\) von Bedeutung.  
  
 Nur **\/NOLOGO** und **\/o** sind innerhalb der Visual Studio\-Entwicklungsumgebung verfügbar.  Informationen über den Zugriff auf die Eigenschaftenseiten des Projekts finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
 \/Ei \( `filename`...\)  
 Schließt den Inhalt der angegebenen Includedateien aus der Browserinformationsdatei aus.  Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden.  Wenn nur ein `filename` angegeben wird, sind runde Klammern nicht erforderlich.  Verwenden Sie **\/Ei** zusammen mit der **\/Es**\-Option, um Dateien auszuschließen, die nicht durch **\/Es** ausgeschlossen werden.  
  
 \/El  
 Schließt lokale Symbole aus.  Standardmäßig werden lokale Symbole eingeschlossen.  Weitere Informationen über lokale Symbole finden Sie unter [Erstellen einer SBR\-Datei](../../build/reference/creating-an-dot-sbr-file.md).  
  
 \/Em  
 Schließt Symbole in Makros aus.  Verwenden Sie **\/Em**, um nur die Namen von Makros in die Browserinformationsdatei einzuschließen.  Standardmäßig werden Makronamen und das Ergebnis der Makroerweiterungen eingeschlossen.  
  
 \/Er \(`symbol`...\)  
 Schließt die angegebenen Symbole aus der Browserinformationsdatei aus.  Bei der Angabe mehrerer Symbolnamen müssen diese durch ein Leerzeichen getrennt und die Liste in runde Klammern eingeschlossen werden.  Wenn nur ein `symbol` angegeben wird, sind runde Klammern nicht erforderlich.  
  
 \/Es  
 Schließt die Includedateien, die mit einem absoluten Pfad angegeben oder in einem absoluten Pfad gefunden werden, der in der INCLUDE\-Umgebungsvariablen angegeben ist, aus der Browserinformationsdatei aus. \(Gewöhnlich sind dies die Includedateien des Systems, die viele Informationen enthalten, die in der Browserinformationsdatei möglicherweise nicht benötigt werden.\) Diese Option schließt keine Dateien aus, die ohne Pfad oder mit einem relativen Pfad angegeben sind oder in einem relativen Pfad in INCLUDE gefunden werden.  Sie können die **\/Ei**\-Option zusammen mit **\/Es** einsetzen, um Dateien auszuschließen, die nicht von **\/Es** ausgeschlossen werden.  Wenn Sie nur einige der Dateien ausschließen möchten, die **\/Es** ausschließt, verwenden Sie **\/Ei** anstelle von **\/Es** und führen die auszuschließenden Dateien auf.  
  
 \/errorreport:\[none &#124; prompt &#124; queue &#124; send\]  
 Ermöglicht das Senden von Informationen in Bezug auf interne Fehler in bscmake.exe an Microsoft.  
  
 Weitere Information zu **\/errorreport** finden Sie unter [\/errorReport \(Meldung über interne Compilerfehler\)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 \/HELP  
 Zeigt eine Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.  
  
 \/Iu  
 Schließt Symbole ein, auf die nicht verwiesen wird.  Standardmäßig zeichnet BSCMAKE keine Symbole auf, die zwar definiert sind, auf die aber nicht verwiesen wird.  Wenn eine SBR\-Datei komprimiert wurde, hat diese Option für diese Eingabedatei keine Auswirkungen, da der Compiler bereits die Symbole entfernt hat, auf die nicht verwiesen wird.  
  
 \/n  
 Erzwingt ein nicht inkrementelles Erstellen.  Verwenden Sie **\/n**, um die Browserinformationsdatei unabhängig vom Vorhandensein einer BSC\-Datei vollständig zu erstellen. Gleichzeitig verhindern Sie so, dass SBR\-Dateien abgeschnitten werden.  Siehe [Erstellen einer BSC\-Datei mit BSCMAKE](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md).  
  
 \/NOLOGO  
 Unterdrückt die Copyrightmeldung von BSCMAKE.  
  
 \/o `filename`  
 Gibt einen Namen für die Browserinformationsdatei an.  Standardmäßig gibt BSCMAKE der Browserinformationsdatei den Basisnamen der ersten SBR\-Datei mit der Erweiterung BSC.  
  
 \/S \( `filename`...\)  
 Weist BSCMAKE an, die angegebene Includedatei bei deren ersten Auftreten zu verarbeiten und ansonsten auszuschließen.  Mit dieser Option kann Verarbeitungszeit eingespart werden, wenn eine Datei, beispielsweise eine Headerdatei \(.h\-Datei\) für eine C\- oder CPP\-Quelldatei, in verschiedene Quelldateien miteinbezogen, aber jeweils nicht von Präprozessordirektiven geändert wird.  Diese Option kann auch verwendet werden, wenn die Änderungen an einer Datei für die zu erstellende Browserinformationsdatei nicht relevant sind.  Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden.  Wenn nur ein `filename` angegeben wird, sind runde Klammern nicht erforderlich.  Wenn die Datei jedes Mal ausgeschlossen werden soll, wenn sie eingeschlossen wird, verwenden Sie die Option **\/Ei** oder **\/Es**.  
  
 \/v  
 Erzeugt eine ausführliche Ausgabe, die den Namen jeder verarbeiteten SBR\-Datei sowie Informationen über die gesamte BSCMAKE\-Ausführung einschließt.  
  
 \/?  
 Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.  
  
 Mit der nachfolgenden Befehlszeile wird BSCMAKE veranlasst, eine vollständige Erstellung der Datei "MAIN.bsc" anhand von drei SBR\-Dateien durchzuführen.  Dabei sollen doppelte Instanzen von TOOLBOX.H ausgeschlossen werden:  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## Siehe auch  
 [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md)