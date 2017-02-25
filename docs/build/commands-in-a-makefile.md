---
title: "Befehle in einem Makefile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehle, Makefiles"
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Befehle in einem Makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Von Beschreibungsblöcken oder Rückschlussregeln wird ein Befehlsblock angegeben, der ausgeführt wird, wenn die Abhängigkeit nicht mehr aktuell ist.  Jeder Befehl wird von NMAKE vor der Ausführung angezeigt, es sei denn, **\/S**, **.SILENT**, **\!CMDSWITCHES** oder @ wird verwendet.  Wenn sich ein Beschreibungsblock nicht vor einem Befehlsblock befindet, wird von NMAKE wird nach einer übereinstimmenden Rückschlussregel gesucht.  
  
 Ein Befehlsblock enthält mindestens einen Befehl, der jeweils eine Zeile aufweist.  Es sind keine Leerzeilen zwischen der Abhängigkeit oder der Regel und dem Befehlsblock zulässig.  Es sind jedoch Zeilen zulässig, die lediglich Leerzeichen oder Tabstopps enthalten. Diese Zeilen werden als NULL\-Befehl interpretiert, und es tritt kein Fehler auf.  Leerzeilen zwischen Befehlszeilen sind zulässig.  
  
 Eine Befehlszeile beginnt mit einem oder mehreren Leerzeichen oder Tabstopps.  Ein umgekehrter Schrägstrich \(\\\) vor einer Zeilenendemarke wird als Leerzeichen im Befehl interpretiert. Mit einem umgekehrten Schrägstrich am Zeilenende kann ein Befehl in der nächsten Zeile fortgesetzt werden.  Umgekehrte Schrägstriche werden literal interpretiert, wenn nach einem umgekehrten Schrägstrich ein beliebiges Zeichen \(einschließlich Leerzeichen oder Tabstopps\) folgt.  
  
 Ein Befehl nach einem Semikolon \(;\) kann in einer Abhängigkeitszeile oder Rückschlussregel unabhängig davon stehen, ob ein Befehlsblock folgt:  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## Worüber möchten Sie mehr erfahren?  
 [Befehlsmodifizierer](../build/command-modifiers.md)  
  
 [Syntax für Dateinamenteile](../build/filename-parts-syntax.md)  
  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)  
  
## Siehe auch  
 [NMAKE\-Referenz](../build/nmake-reference.md)