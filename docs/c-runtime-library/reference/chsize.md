---
title: "_chsize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chsize"
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
  - "_chsize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chsize-Funktion"
  - "chsize-Funktion"
  - "Dateien [C++], Ändern der Größe"
  - "Größe"
  - "Größe, Veränderliche Datei"
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chsize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe einer Datei.  Eine sicherere Version ist verfügbar; finden Sie unter [\_chsize\_s](../../c-runtime-library/reference/chsize-s.md).  
  
## Syntax  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der eine geöffnete Datei verweist.  
  
 `size`  
 Neue Länge einer Datei in Bytes.  
  
## Rückgabewert  
 `_chsize` gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wird.  Bei dem Rückgabewert von 1 gibt einen Fehler an: `errno` wird auf `EACCES`, wenn die angegebene Datei mit Zugriff gesperrt ist, `EBADF`, wenn die angegebene Datei schreibgeschützt ist, der ein oder ungültig ist, `ENOSPC`, wenn kein Platz auf dem Gerät vorhanden ist, oder `EINVAL` festgelegt, wenn `size` kleiner als null ist.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_chsize`\-Funktion erweitert oder schneidet die Datei ab, die mit `fd` zur Länge zugeordnet wird, die von `size` angegeben wird.  Die Datei muss in einem Modus geöffnet werden, ermöglicht der zu schreiben.  NULL\-Zeichen \("\\ 0 "\) angefügt werden, wenn sie erweitert wird.  Wenn die Datei abgeschnitten wird, wurden alle Daten vom Ende der komprimierten Datei zur ursprünglichen Größe der Datei verloren.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `size` kleiner ist, oder als `fd` ein ungültiger Dateideskriptor ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_chsize`|\<io.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
  **Dateilänge zuvor: 0**  
**Größe erfolgreich geändert**  
**Dateilänge anschließend: 329678**   
## .NET Framework-Entsprechung  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)