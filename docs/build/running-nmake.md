---
title: "Ausf&#252;hren von NMAKE"
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
  - "Befehlsdateien"
  - "Befehlsdateien, NMAKE"
  - "NMAKE (Programm), Ausführen"
  - "NMAKE (Programm), Ziele"
  - "Antwortdateien, NMAKE"
  - "Ziele"
  - "Ziele, Erstellen"
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Ausf&#252;hren von NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## Hinweise  
 Von NMAKE werden nur angegebene *targets* erstellt oder aber das erste Ziel des Makefiles, wenn keines angegeben ist.  Beim ersten Ziel in einem Makefile kann es sich um ein [Pseudoziel](../build/pseudotargets.md) handeln, das andere Ziele erstellt.  NMAKE verwendet mit **\/F** angegebene Makefiles. Ist **\/F** nicht angegeben, dann wird die Datei **Makefile** im aktuellen Verzeichnis verwendet.  Ist kein Makefile angegeben, werden Rückschlussregeln eingesetzt, um die in der Befehlszeile angegebenen *targets* zu erstellen.  
  
 In der Textdatei \(Antwortdatei\) `commandfile` sind Befehlszeileneingaben enthalten.  Andere Eingaben können sich vor oder hinter **@**`commandfile` befinden.  Ein Pfad ist zulässig.  In der Datei `commandfile` werden Zeilenumbrüche wie Leerzeichen behandelt.  Makrodefinitionen sollten in Anführungszeichen eingeschlossen sein, wenn diese Leerzeichen enthalten.  
  
## Worüber möchten Sie mehr erfahren?  
 [NMAKE\-Optionen](../build/nmake-options.md)  
  
 [Tools.ini und NMAKE](../build/tools-ini-and-nmake.md)  
  
 [Exitcodes von NMAKE](../build/exit-codes-from-nmake.md)  
  
## Siehe auch  
 [NMAKE\-Referenz](../build/nmake-reference.md)