---
title: "_fseek_nolock, _fseeki64_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseek_nolock"
  - "_fseeki64_nolock"
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
apitype: "DLLExport"
f1_keywords: 
  - "_fseek_nolock"
  - "_fseeki64_nolock"
  - "fseek_nolock"
  - "fseeki64_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseek_nolock-Funktion"
  - "_fseeki64_nolock-Funktion"
  - "Dateizeiger [C++], Verschieben"
  - "fseek_nolock-Funktion"
  - "fseeki64_nolock-Funktion"
  - "seek-Dateizeiger"
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _fseek_nolock, _fseeki64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt der Dateizeiger auf einer bestimmten Position.  
  
## Syntax  
  
```  
int _fseek_nolock(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64_nolock(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
 `offset`  
 Anzahl Bytes von `origin.`  
  
 `origin`  
 Startposition.  
  
## Rückgabewert  
 Identisch mit [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md) verwendet.  
  
## Hinweise  
 Diese Funktionen sind die nicht sperrenden Versionen von `fseek` und `_fseeki64`, verwendet.          Diese sind in `fseek` und `_fseeki64` identisch, allerdings werden nicht von der nicht von anderen Threads vor.  Diese Funktionen möglicherweise schneller, weil sie nicht den Mehraufwand durch andere Threads heraus sperren verursachen.  Verwenden Sie diese Funktionen nur in threadsichere Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)