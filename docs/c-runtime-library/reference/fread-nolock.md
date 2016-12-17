---
title: "_fread_nolock"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_fread_nolock"
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
  - "_fread_nolock"
  - "fread_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fread_nolock-Funktion"
  - "Daten [C++], Lesen aus Eingabesteam"
  - "fread_nolock-Funktion"
  - "Lesen von Daten [C++], aus Eingabestreams"
  - "Streams [C++], Lesen von Daten aus"
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _fread_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest Daten aus einem Stream, ohne dass andere Threads zu sperren.  
  
## Syntax  
  
```  
size_t _fread_nolock(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für Daten.  
  
 `size`  
 Elementgröße in Bytes.  
  
 `count`  
 Maximale Anzahl zu lesende Elemente.  
  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
## Rückgabewert  
 Siehe [fread](../../c-runtime-library/reference/fread.md).  
  
## Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fread`.  Sie ist mit `fread` identisch, allerdings wird von nicht stören durch andere Threads vor.  Sie kann schneller, weil sie nicht den Mehraufwand durch andere Threads heraus sperren verursacht.  Verwenden Sie diese Funktion nur in threadsicherer Kontexten Singlethreadanwendung wie Anwendungen oder, wo die aufrufende Handles des Bereichs bereits Isolation Datentabelle.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fread_nolock`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)