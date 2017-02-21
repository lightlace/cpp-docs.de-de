---
title: "Dateien und Streams | Microsoft Docs"
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
  - "Dateien [C++]"
  - "Streams"
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Dateien und Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Programm ist die Zielumgebung kommunizieren, indem Dateien liest und schreibt.  Eine Datei kann sein:  
  
-   Ein Dataset, das Sie bei lesen und schreiben.  
  
-   Ein Stream von Bytes generiert durch ein Programm \(wie eine Pipeline\).  
  
-   Ein Stream von Bytes empfangen von oder zu einem Peripheriegerät gesendet.  
  
 Die letzten zwei Elemente sind die Dateien.  Dateien sind in der Regel das geänderte Möglichkeit, durch die einem Programm interagieren.  Sie bearbeiten alle diese Arten Dateien auf Clientbasis \- \- durch das Bibliotheksfunktionen.  Sie schließen die Standardheader STDIO.H ein, um die meisten dieser Funktionen zu deklarieren.  
  
 Bevor Sie viele der Vorgänge in einer Datei ausführen können, muss die Datei geöffnet werden.  Eine Datei wird, ordnet sie einem Stream verwenden, eine Datenstruktur in der C\-Standardbibliothek Glanze zu vielen Unterschieden zwischen Dateien unterschiedlicher Arten.  Die Bibliothek bleibt der Zustand jedes Streams in ein Objekt vom Typ FILE bei.  
  
 Die Zielumgebung öffnet drei Dateien vor Programmstart.  Sie können eine Datei öffnen, indem Sie die Bibliotheksfunktion [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) mit zwei Argumenten aufrufen. \(Die Funktion `fopen` ist, verwenden Sie stattdessen [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) . veraltet\) Das erste Argument ist ein Dateiname.  Das zweite Argument handelt es sich um eine C\-Zeichenfolge, die angibt:  
  
-   Ob Sie beabsichtigen, Daten aus der Datei zu lesen oder Daten in diese oder sowohl zu schreiben.  
  
-   Ob Sie beabsichtigen, neuen Inhalt für die Datei zu generieren \(oder eine Datei erstellen, wenn sie nicht bereits vorhanden war\) oder vorhandenen Inhalt gesorgt werden.  
  
-   Ob in eine Datei schreibt, können vorhandenen Inhalt ändern sollten Bytes oder am Ende der Datei nur anfügen.  
  
-   Ob Sie einen Textstream oder einen Binärstream bearbeiten möchten.  
  
 Sobald sich die Datei erfolgreich geöffnet, können Sie bestimmen, ob der Stream byteorientiert ist \(ein Bytestrom\) oder weiter ausgerichtet \(ein breiter Stream\).  Ein Stream wird zuerst ungebunden.  Aufrufende bestimmte Funktionen, z des Streams an zu betreiben macht ihn byteorientiert, wenn unbedingt andere Funktionen, können Sie viele orientiertes.  Sobald hergestellt, behält ein Stream die Ausrichtung bei, bis er durch einen Aufruf von [fclose](../c-runtime-library/reference/fclose-fcloseall.md) oder [freopen](../c-runtime-library/reference/freopen-wfreopen.md) wird geschlossen.  
  
 © 1989\-2001 durch P.J.  Plauger und Jim Brodie.  Alle Rechte vorbehalten.  
  
## Siehe auch  
 [Text\- und binäre Streams](../c-runtime-library/text-and-binary-streams.md)   
 [Byte\- und weite Streams](../c-runtime-library/byte-and-wide-streams.md)   
 [Steuern von Streams](../c-runtime-library/controlling-streams.md)   
 [Streamzustände](../c-runtime-library/stream-states.md)