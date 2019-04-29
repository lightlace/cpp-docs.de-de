---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
ms.date: 11/04/2016
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
ms.openlocfilehash: 36d8b0d6480266f86136119a470fb7af5859a5b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332787"
---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

Ruft Informationen über eine geöffnete Datei ab

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor der geöffneten Datei.

*buffer*<br/>
Zeiger auf die Struktur zum Speichern der Ergebnisse

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Dateistatusinformationen abgerufen werden Ein Rückgabewert 1 gibt einen Fehler. Wenn der Dateideskriptor ungültig ist oder *Puffer* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EBADF**, bei einem ungültigen Dateideskriptor oder zu **EINVAL**, wenn *Puffer* ist **NULL**.

## <a name="remarks"></a>Hinweise

Die **_fstat** Funktion ruft Informationen über die geöffnete Datei zugeordneten *fd* und speichert sie in der Struktur verweist *Puffer*. Die **_stat** in sys\stat definierte Struktur enthält die folgenden Felder.

|Feld|Bedeutung|
|-|-|
| **st_atime** | Zeitpunkt des letzten Zugriffs auf die Datei |
| **st_ctime** | Zeitpunkt der Erstellung der Datei. |
| **st_dev** | Wenn ein Gerät *fd*, andernfalls 0. |
| **st_mode** | Bitmaske für Dateimodusinformationen. Die **_S_IFCHR** Bit ist gesetzt, wenn *fd* bezieht sich auf einem Gerät. Die **_S_IFREG** Bit ist gesetzt, wenn *fd* bezieht sich auf eine normale Datei. Die Bits für den Lese-/Schreibzugriff werden gemäß dem Dateiberechtigungsmodus festgelegt. **_S_IFCHR** und andere Konstanten sind in sys\stat definiert. |
| **st_mtime** | Uhrzeit der letzten Änderung der Datei |
| **st_nlink** | Bei Nicht-NTFS-Dateisystemen immer „1“. |
| **st_rdev** | Wenn ein Gerät *fd*, andernfalls 0. |
| **st_size** | Die Länge der Datei in Bytes. |

Wenn *fd* bezieht sich auf einem Gerät der **St_atime**, **St_ctime**, **St_mtime**, und **St_size** Felder sind nicht aussagekräftig.

Da Stat.h den Typ [_dev_t](../../c-runtime-library/standard-types.md) verwendet, der in Types.h definiert ist, müssen Sie Types.h vor Stat.h in Ihrem Code einschließen.

**_fstat64**, verwendet der **__stat64** Struktur, die Datumsangaben der dateierstellung bis 23:59:59, 31. Dezember 3000 UTC; ausgedrückt werden können, während die anderen Funktionen nur Datumsangaben bis 23:59:59 am 18. Januar darstellen 2038, UTC. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.

Varianten dieser Funktionen unterstützen 32-Bit- oder 64-Bit-Zeittypen und 32-Bit- oder 64-Bit-Dateilängen. Das erste numerische Suffix (**32** oder **64**) gibt die Größe der Zeit verwendet; das zweite Suffix ist entweder **i32** oder **i64**, der angibt, ob die Dateigröße als ganze 32-Bit oder 64-Bit-Zahl dargestellt wird.

**_fstat** entspricht **_fstat64i32**, und **Struktur** **_stat** enthält einen 64-Bit-Uhrzeitwert. Dies gilt, es sei denn, **_USE_32BIT_TIME_T** definiert ist, wird in diesem Fall ist das alte Verhalten wirksam. **_fstat** verwendet einen 32-Bit-Uhrzeitwert, und **Struktur** **_stat** enthält einen 32-Bit-Uhrzeitwert. Das gleiche gilt für **_fstati64**.

### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat-Variationen des Uhrzeittyps und Dateilängentyps

|Funktionen|_USE_32BIT_TIME_T definiert?|Uhrzeittyp|Dateilängentyp|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Nicht definiert|64-Bit|32-Bit|
|**_fstat**|Definiert|32-Bit|32-Bit|
|**_fstat32**|Nicht von der Makrodefinition betroffen|32-Bit|32-Bit|
|**_fstat64**|Nicht von der Makrodefinition betroffen|64-Bit|64-Bit|
|**_fstati64**|Nicht definiert|64-Bit|64-Bit|
|**_fstati64**|Definiert|32-Bit|64-Bit|
|**_fstat32i64**|Nicht von der Makrodefinition betroffen|32-Bit|64-Bit|
|**_fstat64i32**|Nicht von der Makrodefinition betroffen|64-Bit|32-Bit|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fstat**|\<sys/stat.h> and \<sys/types.h>|
|**_fstat32**|\<sys/stat.h> and \<sys/types.h>|
|**_fstat64**|\<sys/stat.h> and \<sys/types.h>|
|**_fstati64**|\<sys/stat.h> and \<sys/types.h>|
|**_fstat32i64**|\<sys/stat.h> and \<sys/types.h>|
|**_fstat64i32**|\<sys/stat.h> and \<sys/types.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[_stat- und _wstat-Funktionen](stat-functions.md)<br/>
