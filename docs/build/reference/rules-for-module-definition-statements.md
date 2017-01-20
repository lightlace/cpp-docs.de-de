---
title: "Regeln f&#252;r Moduldefinitionsanweisungen"
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
  - ".def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Moduldefinitionsdateien"
  - "Moduldefinitionsdateien, Anweisungssyntax"
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Regeln f&#252;r Moduldefinitionsanweisungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgenden Syntaxregeln gelten für alle Anweisungen in einer DEF\-Datei.  Andere Regeln, die nur bestimmte Anweisungen betreffen, werden unter den Ausführungen zur jeweiligen Anweisung beschrieben.  
  
-   Bei Anweisungen, Attributschlüsselwörtern und benutzerdefinierten Bezeichnern muss die Groß\-\/Kleinschreibung beachtet werden.  
  
-   Lange Dateinamen, die Leerzeichen oder Semikolons \(;\) enthalten, müssen in Anführungszeichen \("\) eingeschlossen werden.  
  
-   Verwenden Sie eines oder mehrere Leerzeichen, Tabstoppzeichen oder Zeilenumbruchzeichen, um das Schlüsselwort der Anweisung von den Argumenten zu trennen und um mehrere Anweisungen voneinander zu trennen.  Ein Doppelpunkt \(:\) oder Gleichheitszeichen \(\=\), der bzw. das ein Argument kennzeichnet, ist von keinem oder mehreren Leerzeichen, Tabstoppzeichen oder Zeilenumbruchzeichen umgeben.  
  
-   Eine **NAME**\-Anweisung oder **LIBRARY**\-Anweisung muss, sofern verwendet, vor allen anderen Anweisungen stehen.  
  
-   Die Anweisungen **SECTIONS** und **EXPORTS** können mehr als einmal in der DEF\-Datei auftreten.  Jede Anweisung kann Mehrfachangaben enthalten, die durch eines oder mehrere Leerzeichen, Tabstoppzeichen oder Zeilenumbruchzeichen voneinander getrennt werden müssen.  Das Anweisungsschlüsselwort muss einmal vor der ersten Angabe genannt werden, kann aber auch vor jeder weiteren Angabe wiederholt werden.  
  
-   Viele Anweisungen verfügen über äquivalente **LINK**\-Befehlszeilenoptionen.  Weitere Einzelheiten finden Sie in der Beschreibung der entsprechenden **LINK**\-Option.  
  
-   In der DEF\-Datei werden Kommentare durch ein Semikolon \(;\) am Anfang jeder Kommentarzeile gekennzeichnet.  Ein Kommentar kann nicht zugleich mit einer Anweisung in einer Zeile stehen; zwischen den Angaben in einer mehrzeiligen Anweisung können jedoch Kommentarzeilen eingefügt werden. \(**SECTIONS** und **EXPORTS** sind mehrzeilige Anweisungen.\)  
  
-   Numerische Argumente werden im Basis 10\- oder Hexadezimalformat angegeben.  
  
-   Wenn ein Zeichenfolgenargument mit einem [reservierten Wort](../../build/reference/reserved-words.md) übereinstimmt, muss es in doppelten Anführungszeichen \("\) eingeschlossen werden.  
  
## Siehe auch  
 [Moduldefinitionsdateien \(.Def\)](../../build/reference/module-definition-dot-def-files.md)   
 [Frequently Asked Questions on Building](assetId:///56a3bb8f-0181-4989-bab4-a07ba950ab08)