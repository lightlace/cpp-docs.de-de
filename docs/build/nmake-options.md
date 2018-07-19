---
title: NMAKE-Optionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, options
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2f7ad294a9f199d5dbe6821c61317ed0b6b2693
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373035"
---
# <a name="nmake-options"></a>NMAKE-Optionen
NMAKE-Optionen werden in der folgenden Tabelle beschrieben. Optionen, die durch einen Schrägstrich (/) oder einen Bindestrich (-) vorangestellt werden und sind nicht Groß-/Kleinschreibung beachtet. Verwendung [! CMDSWITCHES](../build/makefile-preprocessing-directives.md) optionseinstellungen in einem Makefile oder Tools.ini ändern.  
  
|Option|Zweck|  
|------------|-------------|  
|/ A|Erzwingt das Erstellen aller ausgewerteten Ziele, auch wenn nicht in Bezug auf abhängige Dateien sind veraltet. Erstellen von unabhängigen Zielen wird nicht erzwungen werden.|  
|/ B|Erzwingt das Erstellen, selbst wenn die Zeitstempel gleich sind. Nur für sehr schnelle Systeme (Auflösung von zwei Sekunden oder weniger) empfohlen.|  
|/C|Unterdrückt die Standardausgabe, einschließlich schwerwiegende NMAKE-Fehler oder Warnungen, Zeitstempel und NMAKE-Copyrightmeldung. Unterdrückt die vom Stapelverarbeitungsprogramm ausgestellte Warnungen|  
|/D|Zeigt die Zeitstempel jedes ausgewertet Ziel- und abhängigen und einer Nachricht, wenn ein Ziel nicht vorhanden ist. Mit/p für das Debuggen eines Makefiles nützlich. Verwendung **! CMDSWITCHES** zu aktivieren bzw. deaktivieren/d für einen Teil eines Makefiles.|  
|/E|Bewirkt, dass Umgebungsvariablen Makrodefinitionen Makefile zu überschreiben.|  
|/ ERRORREPORT [NONE &AMP;#124; PROMPT &AMP;#124; WARTESCHLANGE &AMP;#124; SENDEN]|Wenn nmake.exe zur Laufzeit fehlschlägt, können Sie die/errorreport verwenden, um Informationen über diese internen Fehler an Microsoft gesendet.<br /><br /> Weitere Informationen zu/errorreport, finden Sie unter [/errorreport (Bericht interne Compilerfehler)](../build/reference/errorreport-report-internal-compiler-errors.md).|  
|/ F `filename`|Gibt an, `filename` als Makefile. Leerzeichen oder Tabstopps können voranstellen `filename`. / F wird einmal für jedes Makefile angeben. Geben Sie zum Bereitstellen eines Makefiles aus der Standardeingabe einen Bindestrich (-) für `filename`, und die Tastatureingabe mit F6 oder STRG + Z.|  
|/ G|Zeigt die mit in die! INCLUDE-Anweisung.  Finden Sie unter [Makefile-Vorverarbeitung Direktiven](../build/makefile-preprocessing-directives.md) für Weitere Informationen.|  
|/ HELP, /?|Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von NMAKE.|  
|/I|Ignoriert Exitcodes von Befehlen, die alle an. Verwenden Sie zum Aktivieren bzw. deaktivieren/i für einen Teil eines Makefiles, **! CMDSWITCHES**. Um Exitcodes für einen Teil eines Makefiles zu ignorieren, verwenden Sie einen Bindestrich (-) Befehlsmodifizierer oder [. IGNORIEREN](../build/dot-directives.md). / K überschreibt, wenn beide angegeben werden.|  
|/ K|Weiterhin nicht verknüpfte Abhängigkeiten zu erstellen, wenn ein Befehl einen Fehler zurückgibt. Außerdem wird eine Warnung ausgegeben, und gibt einen Exitcode von 1 zurück. Standardmäßig wird NMAKE angehalten, wenn jeder Befehl einen Exitcode ungleich NULL zurückgibt. Vom/k generierten Warnungen unterdrückt werden durch/c; / I überschreibt/k, wenn beide angegeben werden.|  
|/ N|Zeigt an, aber nicht Ausführungsbefehle; Präprozessorbefehle werden ausgeführt. Zeigt keine Befehle in rekursiven NMAKE aufrufen. Nützlich zum Debuggen von Makefiles und Zeitstempel überprüfen. Verwenden Sie zum Aktivieren bzw. deaktivieren/n für einen Teil eines Makefiles, **! CMDSWITCHES**.|  
|/NOLOGO|Unterdrückt die Copyrightmeldung von NMAKE.|  
|/P|Zeigt Informationen (Makrodefinitionen, Rückschlussregeln, Ziele, [. SUFFIXEN](../build/dot-directives.md) Liste) an die Standardausgabe, und führt dann den Build. Wenn keine Makefile oder Befehlszeilen Ziel vorhanden ist, wird nur zu Informationszwecken angezeigt. Verwenden Sie zum Debuggen eines Makefiles mit/d.|  
|/ Q|Überprüft die Timestamps von Zielen. den Build wird nicht ausgeführt werden. Wenn nicht jedes beliebige Ziel ist ein Exitcode gleich NULL, wenn alle Ziele auf dem neuesten Stand sind und einen Exitcode zurückgegeben werden soll. Präprozessorbefehle werden ausgeführt. Der Wert ist nützlich, wenn NMAKE aus einer Batchdatei ausführen.|  
|/ R|Löscht die **. SUFFIXE** aus und ignoriert Rückschlussregeln und Makros in der Datei Tools.ini definiert sind oder vordefiniert sind.|  
|/ S|Unterdrückt die Anzeige von ausgeführten Befehle. Um die Anzeige in einem Teil eines Makefiles zu unterdrücken, verwenden Sie die **@** Befehlsmodifizierer oder [. AUTOMATISCHE](../build/dot-directives.md). Verwenden Sie zum Aktivieren bzw. deaktivieren/s für den Teil eines Makefiles, **! CMDSWITCHES**.|  
|/ T|Zeitstempel des Befehlszeilen-Ziele (oder erste Makefileziel) aktualisiert und führt Präprozessorbefehle, jedoch wird den Build nicht ausgeführt.|  
|/U|Muss in Verbindung mit/n verwendet werden NMAKE Inlinedateien sichert, damit, dass die Ausgabe/n als Batchdatei verwendet werden kann.|  
|/ X `filename`|Sendet die Fehlerausgabe in NMAKE `filename` anstelle des Standard-Fehlers. Leerzeichen oder Tabstopps können voranstellen `filename`. Um die Fehlerausgabe in die Standardausgabe zu senden, geben Sie einen Bindestrich (-) für `filename`. Die Ausgabe von Befehlen an Standardfehler hat keine Auswirkungen.|  
|/ Y|Deaktiviert die Batchmodus Rückschlussregeln. Wenn diese Option aktiviert ist, werden alle im Batchmodus-Rückschlussregeln als reguläre Rückschlussregeln behandelt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)