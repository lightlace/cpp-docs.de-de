---
title: "NMAKE-Optionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE (Programm), Optionen"
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE-Optionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die NMAKE\-Optionen werden in der folgenden Tabelle beschrieben.  Den Optionen steht entweder ein Schrägstrich \(\/\) oder ein Gedankenstrich \(–\) voran. Bei den Optionen wird außerdem die Groß\-\/Kleinschreibung nicht beachtet.  Mit [\!CMDSWITCHES](../build/makefile-preprocessing-directives.md) können die Optionseinstellungen in einem Makefile oder in der Datei Tools.ini geändert werden.  
  
|Option|Zweck|  
|------------|-----------|  
|\/A|Erzwingt das Erstellen ausgewerteter Ziele auch dann, wenn diese in Bezug auf abhängige Dateien das aktuelle Format aufweisen.  Das Erstellen von unabhängigen Zielen wird nicht erzwungen.|  
|\/B|Erzwingt das Erstellen auch bei gleichen Timestamps.  Nur für sehr schnelle Systeme mit einer Auflösung von höchstens zwei Sekunden empfohlen.|  
|\/C|Unterdrückt die Standardausgabe sowie nicht schwerwiegende NMAKE\-Fehler oder Warnungen, Timestamps und die Copyrightmeldung von NMAKE.  Unterdrückt Warnungen, die durch \/K ausgegeben werden.|  
|\/D|Zeigt Timestamps von allen ausgewerteten Zielen und abhängigen Dateien sowie eine Meldung an, wenn ein Ziel nicht vorhanden ist.  Diese Option kann in Verbindung mit \/P für das Debuggen eines Makefiles verwendet werden.  Mit **\!CMDSWITCHES** kann \/D für einen Teil eines Makefiles festgelegt oder gelöscht werden.|  
|\/E|Veranlasst, dass Umgebungsvariablen Makrodefinitionen eines Makefiles überschreiben.|  
|\/ERRORREPORT\[NONE &#124; PROMPT &#124; QUEUE &#124; SEND \]|Wenn die Ausführung von nmake.exe zur Laufzeit fehlschlägt, können mit \/ERRORREPORT Informationen über diese internen Fehler an Microsoft gesendet werden.<br /><br /> Weitere Informationen über \/ERRORREPORT finden Sie unter [\/errorReport \(Meldung über interne Compilerfehler\)](../build/reference/errorreport-report-internal-compiler-errors.md).|  
|\/F `filename`|Gibt `filename` als Makefile an.  Vor `filename` können Leerzeichen oder Tabstopps stehen.  \/F muss einmal für jedes Makefile angegeben werden.  Um ein Makefile von der Standardeingabe anzugeben, wird ein Gedankenstrich \(–\) für `filename` angegeben, und die Tastatureingabe mit F6 oder STRG\+Z beendet.|  
|\/G|Zeigt die in der \!INCLUDE\-Direktive enthaltenen Makefiles an.  Weitere Informationen finden Sie unter [Direktiven für den Präprozessorlauf eines Makefiles](../build/makefile-preprocessing-directives.md).|  
|\/HELP, \/?|Zeigt eine kurze Zusammenfassung der NMAKE\-Befehlszeilensyntax an.|  
|\/I|Ignoriert Exitcodes von allen Befehlen.  Mit **\!CMDSWITCHES** kann \/I für einen Teil eines Makefiles festgelegt oder gelöscht werden.  Um Exitcodes für einen Teil eines Makefiles zu ignorieren, wird als Befehlsmodifizierer ein Gedankenstrich \(**–**\) oder [.IGNORE](../build/dot-directives.md) verwendet.  Überschreibt \/K, wenn beides angegeben ist.|  
|\/K|Fährt mit dem Erstellen voneinander unabhängiger Abhängigkeiten fort, wenn ein Befehl einen Fehler zurückgibt.  Außerdem wird eine Warnung sowie der Exitcode 1 zurückgegeben.  Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode zurückgibt, der nicht null ist.  Warnungen von \/K werden von \/C unterdrückt. \/I überschreibt \/K, wenn beide angegeben sind.|  
|\/N|Zeigt Befehle an, ohne diese auszuführen. Präprozessorbefehle werden ausgeführt.  Zeigt keine Befehle in rekursiven NMAKE\-Aufrufen an.  Wird für das Debuggen von Makefiles und zum Prüfen von Timestamps verwendet.  Mit **\!CMDSWITCHES** kann \/N für einen Teil eines Makefiles festgelegt oder gelöscht werden.|  
|\/NOLOGO|Unterdrückt die Copyrightmeldung von NMAKE.|  
|\/P|Zeigt Informationen \(Makrodefinitionen, Rückschlussregeln, Ziele und die [.SUFFIXES](../build/dot-directives.md)\-Liste\) in der Standardausgabe an und startet anschließend das Build.  Wenn kein Makefile oder kein Befehlszeilenziel vorhanden ist, werden nur Informationen angezeigt.  Mit \/D kann ein Makefile gedebuggt werden.|  
|\/Q|Prüft Timestamps von Zielen. Es wird kein Build ausgeführt.  Gibt einen Exitcode gleich null zurück, wenn die Ziele aktuell sind. Andernfalls wird ein Exitcode ungleich null zurückgegeben.  Präprozessorbefehle werden ausgeführt.  Wird beim Ausführen von NMAKE aus einer Batchdatei verwendet.|  
|\/R|Löscht die **.SUFFIXES**\-Liste und ignoriert Rückschlussregeln sowie Makros, die in der Datei "Tools.ini" definiert oder vordefiniert sind.|  
|\/S|Unterdrückt die Anzeige von ausgeführten Befehlen.  Um die Anzeige in einem Teil eines Makefiles zu unterdrücken, wird der **@**\-Befehlsmodifizierer oder [.SILENT](../build/dot-directives.md) verwendet.  Mit **\!CMDSWITCHES** kann \/S für einen Teil eines Makefiles festgelegt oder gelöscht werden.|  
|\/T|Aktualisiert Timestamps von Befehlszeilenzielen \(oder dem ersten Makefileziel\) und führt Präprozessorbefehle aus. Das Build wird jedoch nicht ausgeführt.|  
|\/U|Muss in Verbindung mit \/N verwendet werden.  Sichert Inline\-NMAKE\-Dateien, damit die \/N\-Ausgabe als Batchdatei verwendet werden kann.|  
|\/X `filename`|Sendet anstelle eines Standardfehlers eine NMAKE\-Fehlerausgabe an `filename`.  Vor `filename` können Leerzeichen oder Tabstopps stehen.  Um die Fehlerausgabe an die Standardausgabe zu senden, muss ein Gedankenstrich \(\-\) für `filename` angegeben werden.  Wirkt sich nicht auf die Ausgabe von Befehlen an Standardfehler aus.|  
|\/Y|Deaktiviert die Batchmodus\-Rückschlussregeln.  Wenn diese Option aktiviert ist, werden die Rückschlussregeln des Batchmodus als reguläre Rückschlussregeln behandelt.|  
  
## Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)