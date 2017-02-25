---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fstat32"
  - "_fstat64"
  - "_fstati64"
  - "_fstat"
  - "_fstat64i32"
  - "_fstat32i64"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstat32i64"
  - "fstat"
  - "fstat64i32"
  - "_fstat64"
  - "_fstati64"
  - "fstat64"
  - "_fstat32"
  - "fstat32i64"
  - "fstati64"
  - "_fstat"
  - "fstat32"
  - "_fstat64i32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstat64-Funktion"
  - "fstati64-Funktion"
  - "_fstat64i32-Funktion"
  - "_fstat32i64-Funktion"
  - "_fstat32-Funktion"
  - "Dateiinformationen"
  - "fstat64i32-Funktion"
  - "fstat32-Funktion"
  - "fstat-Funktion"
  - "fstat64-Funktion"
  - "_fstat-Funktion"
  - "_fstati64-Funktion"
  - "fstat32i64-Funktion"
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Informationen über eine geöffnete Datei.  
  
## Syntax  
  
```  
int _fstat(   
   int fd,  
   struct _stat *buffer   
);  
int _fstat32(   
   int fd,  
   struct __stat32 *buffer   
);  
int _fstat64(   
   int fd,  
   struct __stat64 *buffer   
);  
int _fstati64(   
   int fd,  
   struct _stati64 *buffer   
);  
int _fstat32i64(   
   int fd,  
   struct _stat32i64 *buffer   
);  
int _fstat64i32(   
   int fd,  
   struct _stat64i32 *buffer   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor der geöffneten Datei.  
  
 `buffer`  
 Zeiger auf die Struktur zum Speichern der Ergebnisse.  
  
## Rückgabewert  
 Gibt 0 zurück, wenn die Datei Statusinformationen abgerufen wird. Ein Rückgabewert von –1 zeigt einen Fehler an. Wenn der Dateideskriptor ungültig ist oder `buffer` ist `NULL`, Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, `errno` Wert `EBADF`, bei der ein ungültiger Dateideskriptor oder zu `EINVAL`, wenn `buffer` ist `NULL`.  
  
## Hinweise  
 Die `_fstat` Funktion ruft Informationen über die geöffnete Datei zugeordneten `fd` und speichert sie in der Struktur auf den `buffer`. Die `_stat` definiert, die in sys\\stat, enthält die folgenden Felder.  
  
 `st_atime`  
 Zeitpunkt des letzten Zugriffs für die Datei.  
  
 `st_ctime`  
 Zeitpunkt der Erstellung der Datei.  
  
 `st_dev`  
 Wenn ein Gerät `fd`; andernfalls 0.  
  
 `st_mode`  
 Bitmaske für Dateimodusinformationen. Das `_S_IFCHR` Bit festgelegt ist, wenn `fd` verweist auf ein Gerät. Das `_S_IFREG` Bit festgelegt ist, wenn `fd` bezieht sich auf eine normale Datei. Die Lese\-\/Schreibzugriff Bits werden gemäß der Datei Berechtigungsmodus festgelegt.`_S_IFCHR` und andere Konstanten in sys\\stat definiert sind.  
  
 `st_mtime`  
 Zeitpunkt der letzten Änderung der Datei.  
  
 `st_nlink`  
 Bei Nicht\-NTFS\-Dateisystemen immer „1“.  
  
 `st_rdev`  
 Wenn ein Gerät `fd`; andernfalls 0.  
  
 `st_size`  
 Die Größe der Datei in Bytes.  
  
 Wenn `fd` bezieht sich auf ein Gerät, das `st_atime`, `st_ctime`, `st_mtime`, und `st_size` Felder haben keine Bedeutung.  
  
 Da Stat.h verwendet die [\_dev\_t](../../c-runtime-library/standard-types.md) geben, die in Types.h definiert ist, müssen Sie Types.h vor Stat.h in Ihren Code aufnehmen.  
  
 `_fstat64`, verwendet der `__stat64` \-Struktur, Datei\-Erstellung von ausgedrückt werden, bis 23:59:59, 31. Dezember 3000, UTC; ermöglicht, während die anderen Funktionen nur Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellen. Mitternacht, ist 1. Januar 1970, die Untergrenze des Zeitraums für alle diese Funktionen.  
  
 Varianten dieser Funktionen unterstützt 32\-Bit\- oder 64\-Bit\-Uhrzeit\-Datentypen und Längen von 32\-Bit\- oder 64\-Bit\-Datei. Das erste numerische Suffix \(`32` oder `64`\) gibt die Größe des verwendeten Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64` und gibt an, ob die Dateigröße als ganze Zahl mit 32 Bit oder 64 Bit dargestellt ist.  
  
 `_fstat` entspricht dem `_fstat64i32`, und `struct``_stat` enthält eine 64\-Bit\-Uhrzeit. Dies ist der Fall, wenn `_USE_32BIT_TIME_T` definiert ist, wird in diesem Fall wird das alte Verhalten aktiviert; `_fstat` verwendet eine 32\-Bit\-Zeit und `struct``_stat` enthält eine 32\-Bit\-Uhrzeit. Das gleiche gilt für `_fstati64`.  
  
### \_stat\-Variationen des Uhrzeittyps und Dateilängentyps  
  
|Funktionen|\_USE\_32BIT\_TIME\_T definiert?|Uhrzeittyp|Dateilängentyp|  
|----------------|--------------------------------------|----------------|--------------------|  
|`_fstat`|Nicht definiert|64\-Bit|32\-Bit|  
|`_fstat`|Definiert|32\-Bit|32\-Bit|  
|`_fstat32`|Nicht von der Makrodefinition betroffen|32\-Bit|32\-Bit|  
|`_fstat64`|Nicht von der Makrodefinition betroffen|64\-Bit|64\-Bit|  
|`_fstati64`|Nicht definiert|64\-Bit|64\-Bit|  
|`_fstati64`|Definiert|32\-Bit|64\-Bit|  
|`_fstat32i64`|Nicht von der Makrodefinition betroffen|32\-Bit|64\-Bit|  
|`_fstat64i32`|Nicht von der Makrodefinition betroffen|64\-Bit|32\-Bit|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fstat`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
|`_fstat32`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
|`_fstat64`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
|`_fstati64`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
|`_fstat32i64`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
|`_fstat64i32`|\< sys\/Stat.h \> und \< sys\/types.h \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fstat.c  
// This program uses _fstat to report  
// the size of a file named F_STAT.OUT.  
  
#include <io.h>  
#include <fcntl.h>  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <errno.h>  
#include <share.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int fd, result;  
   char buffer[] = "A line to output";  
   char timebuf[26];  
   errno_t err;  
  
   _sopen_s( &fd,  
             "f_stat.out",  
             _O_CREAT | _O_WRONLY | _O_TRUNC,  
             _SH_DENYNO,  
             _S_IREAD | _S_IWRITE );  
   if( fd != -1 )  
      _write( fd, buffer, strlen( buffer ) );  
  
   // Get data associated with "fd":   
   result = _fstat( fd, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      if (errno == EBADF)  
        printf( "Bad file descriptor.\n" );  
      else if (errno == EINVAL)  
        printf( "Invalid argument to _fstat.\n" );  
   }  
   else  
   {  
      printf( "File size     : %ld\n", buf.st_size );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid argument to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
   _close( fd );  
}  
```  
  
```Output  
Dateigröße: 16 Änderung: mi Mai 07 15:25:11 2003  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)