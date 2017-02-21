---
title: "R&#252;ckschlussregeln | Microsoft Docs"
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
  - "Rückschlussregeln in NMAKE"
  - "NMAKE (Programm), Rückschlussregeln"
  - "Regeln, Rückschluss"
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# R&#252;ckschlussregeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rückschlussregeln geben Befehle zum Aktualisieren von Zielen und zum Ableiten von abhängigen Dateien für Ziele an.  Erweiterungen in einer Rückschlussregel stimmen mit einem einzelnen Ziel und einer abhängigen Datei überein, die den gleichen Basisnamen besitzen.  Rückschlussregeln sind benutzerdefiniert oder vordefiniert. Vordefinierte Regeln können neu definiert werden.  
  
 Wenn eine nicht mehr aktuelle Abhängigkeit keine Befehle und [.SUFFIXES](../build/dot-directives.md) die Erweiterung der abhängigen Datei enthält, wird von NMAKE eine Regel verwendet, deren Erweiterungen mit dem Ziel und einer vorhandenen Datei im aktuellen oder angegebenen Verzeichnis übereinstimmen.  Wenn mehrere Regeln mit vorhandenen Dateien übereinstimmen, wird von der **.SUFFIXES**\-Liste bestimmt, welche Regel verwendet wird. Die Listenpriorität verläuft von links nach rechts in absteigender Reihenfolge.  Wenn eine abhängige Datei nicht vorhanden und nicht als Ziel in einem anderen Beschreibungsblock aufgelistet ist, kann eine Rückschlussregel die fehlende abhängige Datei aus einer anderen Datei mit dem gleichen Basisnamen erstellen.  Wenn das Ziel eines Beschreibungsblockes keine abhängigen Dateien oder Befehle enthält, kann eine Rückschlussregel das Ziel aktualisieren.  Rückschlussregeln können ein Befehlszeilenziel auch dann erstellen, wenn kein Beschreibungsblock vorhanden ist.  Eine Regel für eine hergeleitete abhängige Datei kann von NMAKE auch dann aufgerufen werden, wenn eine explizite abhängige Datei angegeben ist.  
  
## Worüber möchten Sie mehr erfahren?  
 [Definieren einer Regel](../build/defining-a-rule.md)  
  
 [Stapelverarbeitungsregeln](../build/batch-mode-rules.md)  
  
 [Vordefinierte Regeln](../build/predefined-rules.md)  
  
 [Hergeleitete abhängige Dateien und Regeln](../build/inferred-dependents-and-rules.md)  
  
 [Vorrang in Rückschlussregeln](../build/precedence-in-inference-rules.md)  
  
## Siehe auch  
 [NMAKE\-Referenz](../build/nmake-reference.md)