---
title: "Funktionsweise eines Streams | Microsoft Docs"
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
  - "Daten [C++], Lesen"
  - "Lesen von Daten [C++], iostream-Programmierung"
  - "Streams [C++]"
  - "Streams [C++], in iostream-Klassen"
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Funktionsweise eines Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie C sind C\+\+ nicht integrierte Eingabe\/Ausgabe\-Funktion.  Alle C\+\+\-Compiler jedoch ergeben gebündelt mit einem auf systematische, objektorientierten E\/A\-Paket, wird als das der iostream\-Headerdatei klassifiziert.  Der Stream ist der Leitbegriff der iostream\-Bibliothek Klassen.  Sie können mit einem Streamobjekt als intelligente Datei vorstellen, die als Datenquelle und ein Ziel für Bytes auftritt.  Die Eigenschaften eines Streams werden aus seiner Klasse und aus benutzerdefinierten Einfügungs\- und Extraktionsoperatoren bestimmt.  
  
 Durch Gerätetreiber verarbeitet das Datenträgerbetriebssystem Tastatur, den Bildschirm, den Drucker und die DFV\-Anschlüsse als erweiterte Dateien.  Die der iostream\-Headerdatei Klassen interagieren mit diesen erweiterten Dateien.  Integrierte Klassen unterstützen Lesen und Schreiben im Arbeitsspeicher mit der Syntax, bei der für Datenträger\-E\/A identisch ist, die es erleichtert, Streamklassen zu berechnen macht.  
  
## In diesem Abschnitt  
 [Eingabe\-\/Ausgabealternativen](../standard-library/input-output-alternatives.md)  
  
## Siehe auch  
 [iostream\-Programmierung](../standard-library/iostream-programming.md)