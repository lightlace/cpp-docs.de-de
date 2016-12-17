---
title: "Direktiven f&#252;r den Pr&#228;prozessorlauf eines Makefiles"
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
  - "!UNDEF"
  - "!INCLUDE"
  - "!IFNDEF"
  - "!MESSAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!CMDSWITCHES-Direktive"
  - "!ELSE-Direktive"
  - "!ELSEIF-Direktive"
  - "!ELSEIFDEF-Direktive"
  - "!ELSEIFNDEF-Direktive"
  - "!ENDIF-Direktive"
  - "!ERROR-Direktive"
  - "!IF-Direktive"
  - "!IFDEF-Direktive"
  - "!IFNDEF-Direktive"
  - "!INCLUDE-Direktive"
  - "!MESSAGE-Direktive"
  - "!UNDEF-Direktive"
  - "CMDSWITCHES-Direktive"
  - "Direktiven, Makefile-Vorverarbeitung"
  - "ELSE-Direktive"
  - "ELSEIF-Direktive"
  - "ELSEIFDEF-Direktive"
  - "ELSEIFNDEF-Direktive"
  - "ENDIF-Direktive"
  - "ERROR-Direktive"
  - "IF-Direktive"
  - "IFDEF-Direktive"
  - "IFNDEF-Direktive"
  - "INCLUDE-Direktive"
  - "Makefiles, Präprozessordirektiven"
  - "MESSAGE-Direktive"
  - "NMAKE (Programm), Ausdrücke"
  - "NMAKE (Programm), Präprozessordirektiven"
  - "Präprozessordirektiven, Makefiles"
  - "UNDEF-Direktive"
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Direktiven f&#252;r den Pr&#228;prozessorlauf eines Makefiles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Präprozessordirektiven wird die Groß\-\/Kleinschreibung nicht beachtet.  Das Ausrufungszeichen \(\!\) muss sich am Anfang der Zeile befinden.  Es können sich kein, ein oder mehrere Leerzeichen oder Tabstopps hinter einem Ausrufungszeichen für einen Einzug befinden.  
  
 **\!CMDSWITCHES**  
 {**\+**&#124; **–**}*option*...  Aktiviert bzw. deaktiviert jede aufgelistete *option*.  Leerzeichen oder Tabstopps müssen sich vor den Operatoren \+ oder \- befinden. Sie dürfen nicht zwischen den Operator\- und den [Optionsbuchstaben](../build/nmake-options.md) stehen.  Bei Buchstaben wird die Groß\-\/Kleinschreibung nicht beachtet. Diese werden ohne Schrägstrich \(**\/**\) angegeben.  Um bestimmte Optionen zu aktivieren und zu deaktivieren, werden separate Spezifikationen von **\!CMDSWITCHES** verwendet.  
  
 Nur \/D, \/I, \/N und \/S können in einem Makefile verwendet werden.  In der Datei Tools.ini sind alle Optionen außer \/F, \/HELP, \/NOLOGO, \/X und \/? zulässig.  Änderungen, die in einem Beschreibungsblock angegeben sind, treten erst im nächsten Beschreibungsblock in Kraft.  Diese Direktive aktualisiert **MAKEFLAGS**. Wenn **MAKEFLAGS** angegeben ist, werden Änderungen während der Rekursion geerbt.  
  
 **\!FEHLER**  *Text*  
 Zeigt *Text* im Fehler U1050 an und hält NMAKE anschließend an, und zwar auch dann, wenn \/K, \/I, **.IGNORE, \!CMDSWITCHES** oder der Bindestrich\-Befehlsmodifizierer \(–\) verwendet wird.  Leerzeichen oder Tabstopps vor *text* werden ignoriert.  
  
 **\!MELDUNG**  *Text*  
 Zeigt *text* zur Standardausgabe an.  Leerzeichen oder Tabstopps vor *text* werden ignoriert.  
  
 *Dateiname* **\!INCLUDE**\[ **\<**\] filename \[ **\>**\]  
 Liest *filename* als Makefile und setzt den Vorgang anschließend mit dem aktuellen Makefile fort.  NMAKE\-Suchen für *Dateinamen* zuerst in dem angegebenen oder im aktuellen Verzeichnis, dann rekursiv von Verzeichnissen von einem Elternteilmakefiles dann wenn *Dateiname* von spitzen Klammern \(\< \>\), Verzeichnissen enthalten ist, die vom **INCLUDE**\-Makro angegeben werden, das zunächst auf die INCLUDE\-Umgebungsvariable festgelegt wird.  Wird zum Übergeben von **.SUFFIXES**\-Einstellungen, **.PRECIOUS** und Rückschlussregeln an rekursive Makefiles verwendet.  
  
 **\!IF**  `constantexpression`  
 Verarbeitet Anweisungen zwischen **\!IF** und dem nächsten **\!ELSE** oder `!ENDIF`, wenn `constantexpression` als ein Wert ungleich 0 \(null\) ausgewertet wird.  
  
 **\!IFDEF**  *Makroname*  
 Verarbeitet Anweisungen zwischen \!IFDEF und dem nächsten \!ELSE oder \!ENDIF, wenn *macroname* definiert ist.  Ein NULL\-Makro wird als definiertes Makro angesehen.  
  
 **\!IFNDEF**  *Makroname*  
 Verarbeitet Anweisungen zwischen \!IFDEF und dem nächsten \!ELSE oder \!ENDIF, wenn *macroname* nicht definiert ist.  
  
 **\!ELSE**\[**IF** *konstanterAusdruck* &#124; **IFDEF** *Makroname*&#124; **IFNDEF** *Makroname*\]  
 Verarbeitet Anweisungen zwischen **\!ELSE** und dem nächsten `!ENDIF`, wenn die vorherige **\!IF\-**, **\!IFDEF\-** oder **\!IFNDEF**\-Anweisung als Wert NULL ausgewertet wurde.  Die optionalen Schlüsselwörter bieten eine weitere Steuerung des Präprozessorlaufs.  
  
 **\!ELSEIF**  
 Synonym für **\!ELSE IF**.  
  
 **\!ELSEIFDEF**  
 Synonym für **\!ELSE IFDEF**.  
  
 **\!ELSEIFNDEF**  
 Synonym für **\!ELSE IFNDEF**.  
  
 `!ENDIF`  
 Kennzeichnet das Ende eines **\!IF**\-, `!IFDEF`\- oder **\!IFNDEF**\-Blockes.  Text, der sich nach `!ENDIF` in der gleichen Zeile befindet, wird ignoriert.  
  
 **\!UNDEF**  *Makroname*  
 Hebt die Definition von *macroname* auf.  
  
## Siehe auch  
 [Präprozessorlauf eines Makefiles](../build/makefile-preprocessing.md)