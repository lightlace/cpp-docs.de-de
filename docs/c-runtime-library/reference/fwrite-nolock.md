---
title: "_fwrite_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fwrite_nolock"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fwrite_nolock"
  - "fwrite_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fwrite_nolock-Funktion"
  - "fwrite_nolock-Funktion"
  - "Streams, Schreiben von Daten auf"
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _fwrite_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt Daten an einen Stream, ohne den Thread zu sperren.  
  
## Syntax  
  
```  
size_t _fwrite_nolock(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `buffer`  
 Zeiger auf die Daten geschrieben werden.  
  
 `size`  
 Elementgröße in Bytes.  
  
 `count`  
 Maximale Anzahl Elemente geschrieben werden.  
  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
## Rückgabewert  
 Dieselbe Bedeutung wie [fwrite](../../c-runtime-library/reference/fwrite.md).  
  
## Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fwrite`.  Sie ist mit `fwrite` identisch, allerdings wird von nicht stören durch andere Threads vor.  Sie kann schneller, weil sie nicht den Mehraufwand durch andere Threads heraus sperren verursacht.  Verwenden Sie diese Funktion nur in threadsicherer Kontexten Singlethreadanwendung wie Anwendungen oder, wo die aufrufende Handles des Bereichs bereits Isolation Datentabelle.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fwrite_nolock`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [fread](../../c-runtime-library/reference/fread.md).  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Write](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [\_write](../../c-runtime-library/reference/write.md)