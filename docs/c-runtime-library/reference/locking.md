---
title: "_locking | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_locking"
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
  - "_locking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_locking-Funktion"
  - "Bytes [C++], Sperren einer Datei"
  - "Dateien [C++], Sperren"
  - "Dateien [C++], Sperren von Bytes"
  - "locking-Funktion"
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _locking
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sperrt oder verlagert Bytes einer Datei freigegeben.  
  
## Syntax  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor.  
  
 *mode*  
 Sperrenaktion auszuführen.  
  
 *nbytes*  
 Anzahl Bytes zu sperren.  
  
## Rückgabewert  
 `_locking` gibt 0 zurück, wenn der Vorgang erfolgreich ist.  Bei dem Rückgabewert von 1 Fehler gibt an, in diesem Fall [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf einen der folgenden Werte festgelegt wird.  
  
 `EACCES`  
 Sperrenverletzung \(bereits die gesperrte Datei oder nicht verschlossene\).  
  
 `EBADF`  
 Ungültiger Dateideskriptor.  
  
 `EDEADLOCK`  
 Sperrenverletzung.  Zurückgekehrt, wenn das `_LK_LOCK` oder `_LK_RLCK`\-Flag angegeben ist und die Datei kann nicht gesperrt werden nach 10 Tests.  
  
 `EINVAL`  
 `_locking` wurde ein ungültiges Argument angegeben.  
  
 Wenn der Fehler aufgrund eines ungültigen Parameters, wie ein ungültiger Dateideskriptor, der ungültige Parameterhandler wird aufgerufen wurde, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Hinweise  
 Die `_locking` sperrt Funktion oder setzt *nbytes* Bytes der Datei verwendet, die von `fd` angegeben wird.  Sperrenbytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse.  Alle Sperre oder das Entsperren beginnt in der aktuellen Position des Dateizeigers und Fortfahren für die folgenden *nbytes* Bytes fort.  Es ist möglich, die Bytevergangenheit Dateiende zu sperren.  
  
 *Modus* muss eine der folgenden Manifestkonstanten sein, die in Locking.h definiert werden.  
  
 `_LK_LOCK`  
 Sperrt die angegebenen Bytes.  Wenn die Bytes nicht gesperrt werden, versucht das Programm sofort erneut nach 1 Second.  Wenn, nach 10 Versuchen, die Bytes nicht gesperrt werden können, gibt die Konstante einen Fehler zurück.  
  
 `_LK_NBLCK`  
 Sperrt die angegebenen Bytes.  Wenn die Bytes nicht gesperrt werden können, gibt die Konstante einen Fehler zurück.  
  
 `_LK_NBRLCK`  
 Dieselbe Bedeutung wie `_LK_NBLCK`.  
  
 `_LK_RLCK`  
 Dieselbe Bedeutung wie `_LK_LOCK`.  
  
 `_LK_UNLCK`  
 Setzt die angegebenen Bytes frei, die zuvor gesperrt wurden.  
  
 Mehrere Bereiche einer Datei, die sich nicht überschneiden, können gesperrt werden.  Ein Bereich, der entsperrt wird, muss bereits gesperrt werden.  `_locking` führt nicht aufeinander folgende Bereiche zusammengeführt; wenn zwei gesperrte Bereiche aneinandergrenzen, muss jeder Bereich separat entsperrt werden.  Bereiche dürfen nur kurz gesperrt und sollten entsperrt werden, bevor eine Datei geschlossen oder das Programm beendet.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_locking`|\<io.h und\> sys \<\/locking.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## Eingabe: crt\_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## Beispielausgabe  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)