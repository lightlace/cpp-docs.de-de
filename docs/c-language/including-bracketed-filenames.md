---
title: "Einschlie&#223;lich Dateinamen in Klammern"
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
  - "C"
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Einschlie&#223;lich Dateinamen in Klammern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Die Methode zum Suchen von Quelldateien, die einbezogen werden können  
  
 Der Präprozessor sucht nicht in Verzeichnissen der übergeordneten Dateien nach Dateispezifikationen, die in eckige Klammern eingeschlossen werden.  Eine "übergeordnete" Datei ist die Datei, die die [\#include](../preprocessor/hash-include-directive-c-cpp.md)\-Direktive enthält.  Stattdessen beginnt die Suche nach der Datei in den Verzeichnissen, die in der Compilerbefehlszeile nach "\/I" angegeben werden.  Wenn die \/I\-Option nicht vorhanden ist oder Fehler auftreten, verwendet der Präprozessor die INCLUDE\-Umgebungsvariable, um alle Includedateien in spitzen Klammern zu suchen.  Die INCLUDE\-Umgebungsvariable kann mehrere Pfade enthalten, die durch Semikolons \(**;**\) voneinander getrennt sind.  Wenn mehrere Verzeichnisse in der \/I\-Option oder der INCLUDE\-Umgebungsvariablen enthalten sind, werden diese vom Präprozessor in der Reihenfolge durchsucht, in der sie angezeigt werden.  
  
## Siehe auch  
 [Präprozessordirektiven](../c-language/preprocessing-directives.md)