---
title: "Punktdirektiven | Microsoft Docs"
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
  - "Punktdirektiven in NMAKE"
  - "NMAKE (Programm), Punktdirektiven"
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Punktdirektiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Punktdirektiven werden außerhalb eines Beschreibungsblockes am Zeilenanfang angegeben.  Punktdirektiven beginnen mit einem Punkt \(. \), auf den ein Doppelpunkt \(:\) folgt.  Leerzeichen und Tabstopps sind zulässig.  Bei den Namen von Punktdirektiven wird die Groß\-\/Kleinschreibung beachtet. Die Namen bestehen aus Großbuchstaben.  
  
|Direktive|Zweck|  
|---------------|-----------|  
|**.IGNORE :**|Ignoriert von Befehlen zurückgegebene Exitcodes ungleich null ab der durch die Direktive angegebenen Stelle bis zum Ende des Makefiles.  Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich null zurückgibt.  Mit **\!CMDSWITCHES** kann die Fehlerprüfung wiederhergestellt werden.  Um den Exitcode für einen einzelnen Befehl zu ignorieren, wird der Bindestrichmodifizierer \(**–**\) verwendet.  Mit \/I können Exitcodes für eine gesamte Datei ignoriert werden.|  
|**.PRECIOUS :** *targets*|Behält *targets* auf dem Datenträger, wenn die Befehle für das Aktualisieren der Ziele angehalten werden. Hat keine Auswirkungen, wenn ein Befehl auf eine Unterbrechung durch Löschen der Datei reagiert.  Die Namen der Ziele werden mit einem oder mehreren Leerzeichen oder Tabstopps getrennt.  Standardmäßig wird ein Ziel von NMAKE gelöscht, wenn ein Build durch STRG\+C oder STRG\+UNTBR unterbrochen wird.  **.PRECIOUS** ist für das gesamte Makefile gültig. Mehrere Spezifikationen sind kumulativ.|  
|**.SILENT :**|Unterdrückt die Anzeige von ausgeführten Befehlen ab der Stelle der Angabe bis zum Ende des Makefiles.  Standardmäßig werden aufgerufene Befehle angezeigt.  Mit **\!CMDSWITCHES** kann das Echo wiederhergestellt werden.  Um das Echo für einen einzelnen Befehl zu unterdrücken, wird der **@**\-Modifizierer verwendet.  Mit \/S wird das Echo für eine gesamte Datei unterdrückt.|  
|**.SUFFIXES :** `list`|Listet Erweiterungen für Rückschlussregeln auf, vordefiniert als folgende Dateierweiterungen: .exe .obj .asm .c .cpp .cxx .bas .cbl .for .pas .res .rc .f .f90|  
  
 Um die Reihenfolge der **.SUFFIXES**\-Liste zu ändern oder eine neue Liste anzugeben, wird die Liste gelöscht und dann eine neue Einstellung angegeben.  Um die Liste zu löschen, werden keine Erweiterungen nach dem Doppelpunkt angegeben:  
  
```  
.SUFFIXES :  
```  
  
 Um dem Ende der Liste zusätzliche Suffixe hinzuzufügen, wird Folgendes angegeben:  
  
```  
.SUFFIXES : suffixlist  
```  
  
 Bei *suffixlist* handelt es sich um eine Liste mit zusätzlichen Suffixen, die mit einem oder mehreren Leerzeichen oder Tabstopps getrennt sind.  Um die aktuellen Einstellungen von **.SUFFIXES** anzuzeigen, wird NMAKE mit der \/P\-Option gestartet.  
  
## Siehe auch  
 [NMAKE\-Referenz](../build/nmake-reference.md)