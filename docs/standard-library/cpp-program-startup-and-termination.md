---
title: "Starten und Beenden eines C++-Programms"
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
  - "Steuern von Text-Streams"
  - "Function Main-Prozeduren"
  - "main-Funktion, Programmstart"
  - "C++-Standardbibliothek, Starten und Beenden eines Programms"
  - "Startcode, und C++-Programmbeendigung"
  - "Abbruchsausführung"
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Starten und Beenden eines C++-Programms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

einem C\+\+\-Programm die gleichen Vorgänge ausgeführt werden, die einem C\-Programm beim Programmstart und der dass ausführt, sowie eine aus, die hier beschriebenen.  
  
 Bevor die Zielumgebung die Funktion `main` aufrufen und nachdem alle konstanten Anfangswerte speichert, Sie in allen Objekten, auf die statische Dauer haben, führt das Programm alle übrigen Konstruktoren für solche statischen Objekte aus.  Die Reihenfolge der Ausführung wird nicht zwischen Übersetzungseinheiten angegeben, Sie können aber trotzdem annehmen, dass einige [iostreams](../standard-library/iostreams-conventions.md)\-Objekte ordnungsgemäß für diese statischen Konstruktoren initialisiert werden.  Diese Textgrundlagestreams sind:  
  
-   [cin](../Topic/cin.md) \- für B.  
  
-   [cout](../Topic/cout.md) \- für die Standardausgabe.  
  
-   [cerr](../Topic/cerr.md) \- ungepufferte für Standardfehlerausgabe.  
  
-   [Klotz](../Topic/clog.md) \- Standardfehlerausgabe für gepufferte.  
  
 Sie können diese Objekte mit Destruktoren auch verwenden, die für statische Objekte, dass während der aufgerufen werden.  
  
 Wie mit C, zurückkehrend von `main` oder `exit` Aufruf ruft alle Funktionen in umgekehrter Reihenfolge registriert mit `atexit` der Registrierung auf.  Eine Ausnahme ausgelöst von solchem registrierte Funktionsaufrufe `terminate`.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)