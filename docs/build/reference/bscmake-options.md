---
title: BSCMAKE-Optionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs: C++
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
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 972ac61ff4e838e1c1bf2ad10db50f3a3d595a5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-options"></a>BSCMAKE-Optionen
In diesem Abschnitt werden die Optionen beschrieben, die zur Steuerung von BSCMAKE zur Verfügung stehen. Der Inhalt der Browserinformationsdatei lässt sich durch Ausschließen oder Einschließen bestimmter Informationen mithilfe verschiedener Optionen steuern. Die Ausschlussoptionen ermöglichen eine schnellere Ausführung von BSCMAKE und können eine kleinere BSC-Datei zur Folge haben. Optionsnamen Groß-/Kleinschreibung unterschieden (mit Ausnahme von **/HELP** und **/nologo**).  
  
 Nur **/nologo** und **/o** stehen in der Visual Studio-Entwicklungsumgebung.  Finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md) Zugriff auf Informationen zu Eigenschaftenseiten des Projekts.  
  
 /Ei ( `filename`...)  
 Schließt den Inhalt der angegebenen Includedateien aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden. Wenn nur ein `filename` angegeben wird, sind runde Klammern nicht erforderlich. Verwendung **Ei** zusammen mit den **/es einsetzen** Option zum Ausschließen von Dateien, die nicht ausgeschlossen **/es einsetzen**.  
  
 /El  
 Schließt lokale Symbole aus. Standardmäßig werden lokale Symbole eingeschlossen. Weitere Informationen über lokale Symbole finden Sie unter [Erstellen einer SBR-Datei](../../build/reference/creating-an-dot-sbr-file.md).  
  
 /Em  
 Schließt Symbole in Makros aus. Verwendung **/em** um nur die Namen von Makros in die Browserinformationsdatei einzuschließen. Standardmäßig werden Makronamen und das Ergebnis der Makroerweiterungen eingeschlossen.  
  
 /Er (`symbol`...)  
 Schließt die angegebenen Symbole aus der Browserinformationsdatei aus. Bei der Angabe mehrerer Symbolnamen müssen diese durch ein Leerzeichen getrennt und die Liste in runde Klammern eingeschlossen werden. Wenn nur ein `symbol` angegeben wird, sind runde Klammern nicht erforderlich.  
  
 /Es  
 Schließt die Includedateien, die mit einem absoluten Pfad angegeben oder in einem absoluten Pfad gefunden werden, der in der INCLUDE-Umgebungsvariablen angegeben ist, aus der Browserinformationsdatei aus. (Gewöhnlich sind dies die Includedateien des Systems, die viele Informationen enthalten, die in der Browserinformationsdatei möglicherweise nicht benötigt werden.) Diese Option schließt keine Dateien aus, die ohne Pfad oder mit einem relativen Pfad angegeben sind oder in einem relativen Pfad in INCLUDE gefunden werden. Sie können die **Ei** zusammen mit option **/es einsetzen** einsetzen, um Dateien, die **/es einsetzen** nicht ausgeschlossen. Wenn Sie nur einige der Dateien ausschließen möchten, **/es einsetzen** ausschließt, verwenden Sie **Ei** anstelle von **/es einsetzen** und listet die Dateien, die Sie ausschließen möchten.  
  
 / errorreport: [none &#124; Eingabeaufforderung &#124; Warteschlange &#124; senden]  
 Ermöglicht das Senden von Informationen in Bezug auf interne Fehler in bscmake.exe an Microsoft.  
  
 Weitere Informationen zu **/errorreport**, finden Sie unter [/errorreport (Bericht interne Compilerfehler)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 /HELP  
 Zeigt eine Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.  
  
 /Iu  
 Schließt Symbole ein, auf die nicht verwiesen wird. Standardmäßig zeichnet BSCMAKE keine Symbole auf, die zwar definiert sind, auf die aber nicht verwiesen wird. Wenn eine SBR-Datei komprimiert wurde, hat diese Option für diese Eingabedatei keine Auswirkungen, da der Compiler bereits die Symbole entfernt hat, auf die nicht verwiesen wird.  
  
 /n  
 Erzwingt ein nicht inkrementelles Erstellen. Verwendung  **/n**  einen vollständigen Build der Browserinformationsdatei erzwungen, und zwar unabhängig davon, ob eine BSC-Datei vorhanden ist, und um zu verhindern, dass SBR-Dateien abgeschnitten wird. Finden Sie unter [wie BSCMAKE eine BSC-Datei erstellt](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md).  
  
 /NOLOGO  
 Unterdrückt die Copyrightmeldung von BSCMAKE.  
  
 /o `filename`  
 Gibt einen Namen für die Browserinformationsdatei an. Standardmäßig gibt BSCMAKE der Browserinformationsdatei den Basisnamen der ersten SBR-Datei mit der Erweiterung BSC.  
  
 /S ( `filename`...)  
 Weist BSCMAKE an, die angegebene Includedatei bei deren ersten Auftreten zu verarbeiten und ansonsten auszuschließen. Mit dieser Option kann Verarbeitungszeit eingespart werden, wenn eine Datei, beispielsweise eine Headerdatei (.h-Datei) für eine C- oder CPP-Quelldatei, in verschiedene Quelldateien miteinbezogen, aber jeweils nicht von Präprozessordirektiven geändert wird. Diese Option kann auch verwendet werden, wenn die Änderungen an einer Datei für die zu erstellende Browserinformationsdatei nicht relevant sind. Bei der Angabe mehrerer Dateien müssen deren Namen durch ein Leerzeichen getrennt und die Liste muss in runde Klammern eingeschlossen werden. Wenn nur ein `filename` angegeben wird, sind runde Klammern nicht erforderlich. Wenn Sie verwenden möchten, schließen Sie die Datei jedes Mal, wenn sie eingeschlossen wird, verwenden die **Ei** oder **/es einsetzen** Option.  
  
 /v  
 Erzeugt eine ausführliche Ausgabe, die den Namen jeder verarbeiteten SBR-Datei sowie Informationen über die gesamte BSCMAKE-Ausführung einschließt.  
  
 /?  
 Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von BSCMAKE an.  
  
 Mit der nachfolgenden Befehlszeile wird BSCMAKE veranlasst, eine vollständige Erstellung der Datei "MAIN.bsc" anhand von drei SBR-Dateien durchzuführen. Dabei sollen doppelte Instanzen von TOOLBOX.H ausgeschlossen werden:  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)