---
title: "_filelength, _filelengthi64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_filelengthi64"
  - "_filelength"
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
  - "_filelength"
  - "_filelengthi64"
  - "filelengthi64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_filelength-Funktion"
  - "_filelengthi64-Funktion"
  - "filelength-Funktion"
  - "filelengthi64-Funktion"
  - "Dateien [C++], Länge"
  - "Längen, Datei"
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _filelength, _filelengthi64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Länge einer Datei ab.  
  
## Syntax  
  
```  
long _filelength(   
   int fd   
);  
__int64 _filelengthi64(   
   int fd   
);  
```  
  
#### Parameter  
 `fd`  
 Abzielen auf den Dateideskriptor ab.  
  
## Rückgabewert  
 Geben `_filelength` und `_filelengthi64` die Dateilänge, in Bytes, der Zieldatei zurück, die `fd` zugeordnet ist.  Wenn `fd` ein ungültiger Dateideskriptor ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, geben beide Funktionen \- 1L zurück, um einen Fehler und eine Gruppe von `errno` zu `EBADF`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_filelength`|\<io.h\>|  
|`_filelengthi64`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [\_chsize](../../c-runtime-library/reference/chsize.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)