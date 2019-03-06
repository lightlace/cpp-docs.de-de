---
title: NMAKE-Optionen
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, options
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
ms.openlocfilehash: dca7b94935f385971b8d9bff53ece3b86f2885b8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417072"
---
# <a name="nmake-options"></a>NMAKE-Optionen

NMAKE-Optionen werden in der folgenden Tabelle beschrieben. Optionen, die durch einen Schrägstrich (/) oder einen Bindestrich (-) vorangestellt werden und sind nicht in der Groß-/Kleinschreibung beachtet. Verwendung [! CMDSWITCHES](../build/makefile-preprocessing-directives.md) optionseinstellungen in einem Makefile oder Tools.ini zu ändern.

|Option|Zweck|
|------------|-------------|
|/A|Erzwingt das Erstellen alle ausgewerteten Ziele, auch wenn nicht in Bezug auf abhängige Elemente sind veraltet. Erstellen von unabhängigen Zielen wird nicht erzwungen werden.|
|/B|Erzwingt, dass erstellen, auch wenn die Zeitstempel gleich sind. Nur für sehr schnell Systeme (Auflösung von zwei Sekunden oder weniger) empfohlen.|
|/C|Standardausgabe, einschließlich schwerwiegende NMAKE-Fehler oder Warnungen, Zeitstempel und NMAKE-Copyrightmeldung wird unterdrückt. Vom Stapelverarbeitungsprogramm ausgestellte Warnungen unterdrückt|
|/D|Zeigt die Zeitstempel der einzelnen ausgewertet Ziel und abhängige und eine Nachricht, wenn ein Ziel nicht vorhanden ist. Mit/p für das Debuggen eines Makefiles nützlich. Verwendung **! CMDSWITCHES** zu aktivieren oder deaktivieren Sie/d für den Teil eines Makefiles.|
|/E|Bewirkt, dass Umgebungsvariablen Makefiles Makrodefinitionen zu überschreiben.|
|/ERRORREPORT[NONE &#124; PROMPT &#124; QUEUE &#124; SEND ]|Wenn nmake.exe zur Laufzeit ein Fehler auftritt, können Sie die/errorreport verwenden, um Informationen über diese internen Fehler an Microsoft gesendet.<br /><br /> Weitere Informationen zu/errorreport, finden Sie unter [/errorreport (interne Compilerfehler Bericht)](../build/reference/errorreport-report-internal-compiler-errors.md).|
|/ F *Dateiname*|Gibt an, *Filename* als Makefile. Leerzeichen oder Tabstopps können voranstellen *Filename*. / F wird einmal für jedes Makefile angeben. Um ein Makefile aus der Standardeingabe, geben Sie einen Bindestrich (-) für *Filename*, und Beenden von Tastatureingaben mit F6 oder STRG + Z.|
|/G|Zeigt die mit in der! #INCLUDE-Anweisung.  Finden Sie unter [Direktiven für die Makefile-Vorverarbeitung](../build/makefile-preprocessing-directives.md) für Weitere Informationen.|
|/ HELP, /?|Zeigt eine kurze Zusammenfassung der Befehlszeilensyntax von NMAKE an.|
|/I|Exitcodes von allen Befehlen wird ignoriert. Verwenden, um festzulegen, oder deaktivieren Sie die/i für einen Teil eines Makefiles, **! CMDSWITCHES**. Zum ignorieren Exitcodes für einen Teil eines Makefiles verwenden Sie einen Bindestrich (-) Befehlsmodifizierer oder [. IGNORIEREN Sie](../build/dot-directives.md). / K überschreibt, wenn beide angegeben werden.|
|/K|Wenn ein Befehl einen Fehler zurückgibt, weiterhin nicht verknüpfte Abhängigkeiten zu erstellen. Außerdem gibt eine Warnung aus, und gibt einen Exitcode von 1 zurück. Standardmäßig wird Sie NMAKE angehalten, wenn ein beliebiger Befehl einen Exitcode ungleich NULL zurückgibt. / K Warnungen werden von/c unterdrückt; / I überschreibt/k, wenn beide angegeben werden.|
|/N|Zeigt an, aber keine Befehle ausgeführt werden; vorab verarbeitetes Befehle werden ausgeführt. Befehle wird in rekursiven NMAKE Aufrufen nicht angezeigt werden. Nützlich zum Debuggen von Makefiles und Zeitstempel überprüfen. Verwenden, um festzulegen, oder deaktivieren Sie/n für einen Teil eines Makefiles, **! CMDSWITCHES**.|
|/NOLOGO|NMAKE: Copyrightmeldung wird unterdrückt.|
|/P|Zeigt Informationen an (Makrodefinitionen, Rückschlussregeln, Ziele [. SUFFIXE](../build/dot-directives.md) Liste) an die Standardausgabe, und führt dann den Build. Wenn kein Makefile oder der Befehlszeile Ziel vorhanden ist, wird nur zu Informationszwecken angezeigt. Verwenden Sie mit/d, um ein Makefile zu debuggen.|
|/Q|Überprüft die Timestamps von Zielen. den Build wird nicht ausgeführt werden. Jedes beliebige Ziel ist keinen Exitcode gleich NULL, wenn alle Ziele auf dem neuesten Stand sind und einen Exitcode ungleich NULL zurückgegeben werden soll. Vorab verarbeitetes Befehle werden ausgeführt. Nützlich, wenn NMAKE von einer Batchdatei ausgeführt wird.|
|/R|Löscht die **. SUFFIXE** aus und ignoriert Rückschlussregeln und Makros, die in der Datei Tools.ini definiert oder vordefiniert sind.|
|/S|Unterdrückt die Anzeige der ausgeführten Befehle. Um die Anzeige in einem Teil des ein Makefile zu unterdrücken, verwenden Sie die **\@** Befehlsmodifizierer oder [. AUTOMATISCHE](../build/dot-directives.md). Verwenden, um festzulegen, oder deaktivieren Sie "/ s" für den Teil eines Makefiles, **! CMDSWITCHES**.|
|/T|Zeitstempel der Befehlszeilenziele (oder erste Makefileziel) aktualisiert, und führt Präprozessorbefehle, aber den Build wird nicht ausgeführt.|
|/U|Muss in Verbindung mit/n verwendet werden Sichert Inline NMAKE-Dateien, damit die Ausgabe/n als eine Batchdatei verwendet werden kann.|
|/ X *Dateiname*|NMAKE-Fehlerausgabe in sendet *Filename* anstelle des Standard-Fehlers. Leerzeichen oder Tabstopps können voranstellen *Filename*. Um Fehler bei der Ausgabe an die Standardausgabe zu senden, geben Sie einen Bindestrich (-) für *Filename*. Die Ausgabe von Befehlen an Standardfehler hat keine Auswirkungen.|
|/ Y|Wird im Batchmodus-Rückschlussregeln deaktiviert. Wenn diese Option ausgewählt ist, werden alle im Batchmodus-Rückschlussregeln als reguläre Rückschlussregeln behandelt.|

## <a name="see-also"></a>Siehe auch

[Ausführen von NMAKE](../build/running-nmake.md)
