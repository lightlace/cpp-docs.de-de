---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
dev_langs:
- C++
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: b84c039c715c8c7a45a84a37c1a1fd34db988403
ms.lasthandoff: 02/24/2017

---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
Ruft Informationen über eine geöffnete Datei ab  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor der geöffneten Datei.  
  
 `buffer`  
 Zeiger auf die Struktur zum Speichern der Ergebnisse  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn die Dateistatusinformationen abgerufen werden Ein Rückgabewert von –1 zeigt einen Fehler an. Wenn der Dateideskriptor ungültig oder `buffer` `NULL` ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` im Falle eines ungültigen Dateideskriptors auf `EBADF` festgelegt. Andernfalls wird es auf `EINVAL` festgelegt, wenn `buffer` `NULL` ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_fstat` ruft Informationen zur offenen Datei ab, die mit `fd` verknüpft ist, und speichert sie in der Struktur, auf die `buffer` verweist. Die in SYS\Stat.h definierte Struktur `_stat` enthält die folgenden Felder.  
  
 `st_atime`  
 Zeitpunkt des letzten Zugriffs auf die Datei  
  
 `st_ctime`  
 Zeitpunkt der Erstellung der Datei.  
  
 `st_dev`  
 Wenn es sich um ein Gerät handelt, dann `fd`, andernfalls 0.  
  
 `st_mode`  
 Bitmaske für Dateimodusinformationen. Das Bit `_S_IFCHR` wird festgelegt, wenn `fd` auf ein Gerät verweist. Das Bit `_S_IFREG` wird festgelegt, wenn `fd` auf eine normale Datei verweist. Die Bits für den Lese-/Schreibzugriff werden gemäß dem Dateiberechtigungsmodus festgelegt. `_S_IFCHR` und andere Konstanten sind in SYS\Stat.h definiert.  
  
 `st_mtime`  
 Uhrzeit der letzten Änderung der Datei  
  
 `st_nlink`  
 Bei Nicht-NTFS-Dateisystemen immer „1“.  
  
 `st_rdev`  
 Wenn es sich um ein Gerät handelt, dann `fd`, andernfalls 0.  
  
 `st_size`  
 Die Länge der Datei in Bytes.  
  
 Wenn sich `fd` auf ein Gerät bezieht, sind die Felder `st_atime`, `st_ctime`, `st_mtime` und `st_size` nicht sinnvoll.  
  
 Da Stat.h den Typ [_dev_t](../../c-runtime-library/standard-types.md) verwendet, der in Types.h definiert ist, müssen Sie Types.h vor Stat.h in Ihrem Code einschließen.  
  
 `_fstat64`, das die `__stat64`-Struktur verwendet, ermöglicht es, die Zeitpunkte der Dateierstellung bis 23:59:59 am 31. Dezember 3000 (UTC) anzugeben, während andere Funktionen nur Datumsangaben bis zum 18. Januar 2038, 23:59:59 (UTC) darstellen. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.  
  
 Varianten dieser Funktionen unterstützen 32-Bit- oder 64-Bit-Zeittypen und 32-Bit- oder 64-Bit-Dateilängen. Das erste numerische Suffix (`32` oder `64`) gibt die Größe des verwendeten Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64`und gibt an, ob die Dateigröße als ganze Zahl mit 32 Bit oder 64 Bit dargestellt ist.  
  
 `_fstat` ist äquivalent zu `_fstat64i32`, und `struct``_stat` enthält einen 64-Bit-Uhrzeitwert. Das trifft zu, sofern nicht `_USE_32BIT_TIME_T` definiert wurde; in diesem Fall ist das alte Verhalten wirksam. `_fstat` verwendet einen 32-Bit-Uhrzeitwert, und `struct``_stat` enthält einen 32-Bit-Uhrzeitwert. Gleiches gilt auch für `_fstati64`.  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat-Variationen des Uhrzeittyps und Dateilängentyps  
  
|Funktionen|_USE_32BIT_TIME_T definiert?|Uhrzeittyp|Dateilängentyp|  
|---------------|------------------------------------|---------------|----------------------|  
|`_fstat`|Nicht definiert|64-Bit|32-Bit|  
|`_fstat`|Definiert|32-Bit|32-Bit|  
|`_fstat32`|Nicht von der Makrodefinition betroffen|32-Bit|32-Bit|  
|`_fstat64`|Nicht von der Makrodefinition betroffen|64-Bit|64-Bit|  
|`_fstati64`|Nicht definiert|64-Bit|64-Bit|  
|`_fstati64`|Definiert|32-Bit|64-Bit|  
|`_fstat32i64`|Nicht von der Makrodefinition betroffen|32-Bit|64-Bit|  
|`_fstat64i32`|Nicht von der Makrodefinition betroffen|64-Bit|32-Bit|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fstat`|\<sys/stat.h> and \<sys/types.h>|  
|`_fstat32`|\<sys/stat.h> and \<sys/types.h>|  
|`_fstat64`|\<sys/stat.h> and \<sys/types.h>|  
|`_fstati64`|\<sys/stat.h> and \<sys/types.h>|  
|`_fstat32i64`|\<sys/stat.h> and \<sys/types.h>|  
|`_fstat64i32`|\<sys/stat.h> and \<sys/types.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
File size     : 16  
Time modified : Wed May 07 15:25:11 2003  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_filelength, _filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [_stat- und _wstat-Funktionen](../../c-runtime-library/reference/stat-functions.md)
