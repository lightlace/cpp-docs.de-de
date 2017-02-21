---
title: "Text- und Bin&#228;rmodusdatei-E/A | Microsoft Docs"
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
  - "Binärer Zugriff"
  - "Binärer Zugriff, Binärmodusdatei-E/A"
  - "Dateien [C++], Öffnungsfunktionen"
  - "Funktionen [CRT], Dateizugriff"
  - "E/A [CRT], Binär"
  - "E/A [CRT], Textdateien"
  - "E/A [CRT], Übersetzungsmodi"
  - "Textdateien, E/A"
  - "Übersetzungsmodi (Datei-E/A)"
  - "Verschiebung, Modi"
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Text- und Bin&#228;rmodusdatei-E/A
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Datei\-E\/A\-Operationen werden in einem von zwei Übersetzungsmodi, Text oder Binärdatei, abhängig vom Modus ausgeführt, in dem die Datei geöffnet ist.  Datendateien werden normalerweise im Textmodus verarbeitet.  Um den Dateiübersetzungsmodus steuern, kann einer:  
  
-   Beibehalten der aktuelle Standardeinstellung beibehalten und den alternativen nur an, wenn Sie ausgewählte Dateien öffnen.  
  
-   Verwenden Sie die Funktion [\_set\_fmode](../c-runtime-library/reference/set-fmode.md), um dem Standardmodus für neu geöffnete Dateien zu ändern.  Verwenden Sie [\_get\_fmode](../c-runtime-library/reference/get-fmode.md), um die aktuelle Standardmodus zu suchen.  Die anfängliche Standardeinstellung ist Textmodus \(`_O_TEXT`\).  
  
-   Ändern Sie den Standardübersetzungsmodus, indem Sie direkt die globale Variable [\_fmode](../c-runtime-library/fmode.md) im Programm festlegen.  Die Funktion `_set_fmode` wird der Wert dieser Variable festgelegt, sie kann jedoch auch direkt festgelegt werden.  
  
 Wenn Sie eine DateiOPEN\-Funktion wie [\_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [\_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) oder [\_sopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md) aufrufen, können Sie die aktuelle Standardeinstellung `_fmode` überschreiben, indem Sie das entsprechende Argument für die Funktion [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) angeben.  `stdin`, `stdout` und `stderr` immer Streams öffnen im Textmodus standardmäßig; Sie können diese Standardeinstellung auch überschreiben, wenn Sie Dateien öffnen.  Verwenden Sie [\_setmode](../c-runtime-library/reference/setmode.md), den Übersetzungsmodus mithilfe des Dateideskriptors nach der Datei zu ändern ist geöffnet.  
  
## Siehe auch  
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)