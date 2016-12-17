---
title: "_fflush_nolock"
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
  - "_fflush_nolock"
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
  - "fflush_nolock"
  - "_fflush_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fflush_nolock-Funktion"
  - "fflush_nolock-Funktion"
  - "Leeren"
  - "Streams, Leeren"
ms.assetid: 5e33c4a1-b10c-4001-ad01-210757919291
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _fflush_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Leert einen Stream, ohne den Thread zu sperren.  
  
## Syntax  
  
```  
int _fflush_nolock(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
## Rückgabewert  
 Siehe [fflush](../../c-runtime-library/reference/fflush.md).  
  
## Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fflush`.  Sie ist mit `fflush` identisch, allerdings wird von nicht stören durch andere Threads vor.  Sie kann schneller, weil sie nicht den Mehraufwand durch andere Threads heraus sperren verursacht.  Verwenden Sie diese Funktion nur in threadsicherer Kontexten Singlethreadanwendung wie Anwendungen oder, wo die aufrufende Handles des Bereichs bereits Isolation Datentabelle.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fflush_nolock`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)