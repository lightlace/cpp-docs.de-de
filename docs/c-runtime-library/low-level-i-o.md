---
title: "E/A auf niedriger Ebene | Microsoft Docs"
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
  - "Dateihandles [C++]"
  - "Dateihandles [C++], E/A-Funktionen"
  - "E/A [CRT], Funktionen"
  - "E/A [CRT], Auf niedriger Ebene"
  - "E/A-Routine auf niedriger Ebene"
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# E/A auf niedriger Ebene
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen rufen das Betriebssystem direkt für Vorgang auf niedrigerer Ebene als das auf, das von Stream\-E\/A bereitgestellt wird.  Eingabe\- und Ausgabeaufrufe systemnahe puffern nicht oder formatieren Daten.  
  
 Routinen systemnahe können auf die Standardstreams zugreifen, die beim Programmstart mithilfe der folgenden vordefinierten Dateideskriptoren geöffnet sind.  
  
|Stream|Dateideskriptor|  
|------------|---------------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 E\/A\-Routinen systemnahe legen die globale Variablen [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), wenn ein Fehler auftritt.  Sie müssen STDIO.H einschließen, wenn Sie Funktionen auf niedrigerer Ebene nur verwenden, wenn das Programm eine Konstante, die in STDIO.H definiert wird, wie das Dateiende\-Indikator \(`EOF`\) angegeben.  
  
### E\/A Funktionen auf niedriger Ebene  
  
|Funktion|Verwendung|  
|--------------|----------------|  
|[\_close](../c-runtime-library/reference/close.md)|Geben Datei|  
|[\_commit](../c-runtime-library/reference/commit.md)|Bündige Datei auf Festplatte|  
|[\_creat, \_wcreat](../c-runtime-library/reference/creat-wcreat.md)|Erstellen Sie eine Datei|  
|[\_dup](../c-runtime-library/reference/dup-dup2.md)|Nachfolgender verfügbarer RückholDateideskriptor für angegebene Datei|  
|[\_dup2](../c-runtime-library/reference/dup-dup2.md)|Erstellen Sie zweiten Deskriptor für angegebene Datei|  
|[\_eof](../c-runtime-library/reference/eof.md)|Test für Dateiende|  
|[\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Zuordnen Dateizeiger dem angegebenen Speicherort neu an|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Geöffnete Datei|  
|[\_read](../c-runtime-library/reference/read.md)|statt von Datei|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Geöffnete Datei für den Datenzugriff|  
|[\_tell, \_telli64](../c-runtime-library/reference/tell-telli64.md)|Rufen Sie aktuelle Dateizeigerposition ab|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|Legen Sie Dateiberechtigungsmaske fest|  
|[\_write](../c-runtime-library/reference/write.md)|Schreiben Sie Daten in die Datei|  
  
 `_dup` und `_dup2` werden in der Regel verwendet, um den vordefinierten Dateideskriptoren mit verschiedenen Dateien zuzuordnen.  
  
## Siehe auch  
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Systemaufrufe](../c-runtime-library/system-calls.md)