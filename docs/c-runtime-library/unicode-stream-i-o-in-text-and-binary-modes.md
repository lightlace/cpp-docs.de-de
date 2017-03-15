---
title: "Unicodestream-E/A im Text- und Bin&#228;rmodus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E/A [CRT], Unicode-Stream"
  - "Stream-E/A-Routinen"
  - "Unicodestream-E/A"
  - "Unicode, Stream-E/A-Routinen"
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Unicodestream-E/A im Text- und Bin&#228;rmodus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Unicode\-Stream E\/A\-Routine \(wie `fwprintf`, `fwscanf`, `fgetwc`, `fputwc`, `fgetws` oder `fputws`\) zu einer Datei, wendet die im Textmodus \(Standard\) geöffnet ist, werden zwei Arten Zeichenumsetzungen statt:  
  
-   Unicode\-zu\-MBCS\- oder MBCS\-zu\-Unicode\-Konvertierung.  Wenn eine Funktion von Unicode im stream\-I\/O Textmodus funktioniert, wird der Quell\- oder Zielstream angenommen, um eine Sequenz von Mehrbytezeichen zu sein.  Daher konvertieren die Unicode Streameingabefunktionen Multibytezeichen in Breitzeichen \(wie bei einem Aufruf der `mbtowc`\-Funktion\).  Aus demselben Grund konvertieren die Unicode\-Streamausgabefunktionen Breitzeichen in Multibytezeichen \(wie bei einem Aufruf der `wctomb`\-Funktion\).  
  
-   Übersetzung des Wagenrücklauf\/Zeilenvorschubs \(CR\-LF\).  Diese Übersetzung tritt vor dem MBCS auf \- Unicode\-Konvertierung \(für Unicode\-Stream geben Sie Funktionen\) und nach dem \- Unicode MBCS\-Konvertierung \(für Unicode\-Streamausgabefunktionen\).  Während der Eingabe wird jede Wagenrücklauf\/Zeilenvorschub\-Kombination in ein einzelnes Zeilenvorschubzeichen übersetzt.  Während der Ausgabe wird jedes Zeilenvorschubzeichen in eine Wagenrücklauf\/Zeilenvorschub\-Kombination übersetzt.  
  
 Wenn eine Funktion von Unicode stream\-I\/O im binären Modus ausgeführt wird, die Datei angenommen, um Unicode ist, und keine CR\-LF Übersetzung oder Zeichenkonvertierung tritt während der Eingabe oder die Ausgabe auf.  Verwenden Sie das \_setmode \(\_fileno \(stdin\), \_O\_BINARY\); Anweisung zum wcin auf einer UNICODE\-Textdatei ordnungsgemäß verwenden.  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)