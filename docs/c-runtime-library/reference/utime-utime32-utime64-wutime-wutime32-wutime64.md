---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
ms.date: 11/04/2016
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
ms.openlocfilehash: 8e52845a828e272ff3b8458b299c3757b8def748
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524630"
---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64

Legen Sie die Dateiänderungszeit fest.

## <a name="syntax"></a>Syntax

```C
int _utime(
   const char *filename,
   struct _utimbuf *times
);
int _utime32(
   const char *filename,
   struct __utimbuf32 *times
);
int _utime64(
   const char *filename,
   struct __utimbuf64 *times
);
int _wutime(
   const wchar_t *filename,
   struct _utimbuf *times
);
int _wutime32(
   const wchar_t *filename,
   struct __utimbuf32 *times
);
int _wutime64(
   const wchar_t *filename,
   struct __utimbuf64 *times
);
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Zeiger auf eine Zeichenfolge, die den Pfad oder Dateiname enthält.

*Wie oft*<br/>
Zeiger auf die gespeicherten Zeitwerte.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt „0“ zurück, wenn die Dateiänderungszeit geändert wurde. Ein Rückgabewert 1 gibt einen Fehler. Wird ein ungültiger Parameter übergeben, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und **Errno** auf einen der folgenden Werte festgelegt:

|errno-Wert|Bedingung|
|-|-|
| **EACCES** | Pfad gibt Verzeichnis oder schreibgeschützte Datei an. |
| **EINVAL** | Ungültige *Zeiten* Argument |
| **EMFILE** | Zu viele Dateien geöffnet. (Die Datei muss geöffnet werden, damit die Änderungszeit geändert werden kann.) |
| **ENOENT** | Pfad oder Dateiname wurde nicht gefunden. |

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Wenn das Datum der Änderung nach dem 1. Januar 1970, Mitternacht, und vor dem Enddatum für die Verwendung der Funktion liegt, kann das Datum für eine Datei geändert werden. **_utime** und **_wutime** verwenden einen 64-Bit-Uhrzeitwert, damit das Enddatum 23:59:59, 31. Dezember 3000 UTC ist. Wenn **_USE_32BIT_TIME_T** definiert wird um das alte Verhalten zu erzwingen, ist das Enddatum 23:59:59 am 18. Januar 2038, UTC. **_utime32** oder **_wutime32** verwenden einen 32-Bit-Zeittyp, unabhängig davon, ob **_USE_32BIT_TIME_T** definiert ist, und immer das frühere Enddatum. **_utime64** oder **_wutime64** immer den 64-Bit-Uhrzeittyp verwenden, damit diese Funktionen immer das spätere Enddatum unterstützt.

## <a name="remarks"></a>Hinweise

Die **_utime** Funktion legt das Änderungsdatum für die angegebene Datei *Filename*. Damit die Zeit geändert werden kann, benötigt der Prozess Schreibzugriff für die Datei. Sie können im Windows-Betriebssystem, ändern, Zugriffszeit und Änderungszeit in der **_utimbuf** Struktur. Wenn *Zeiten* ist eine **NULL** -Zeiger ist, wird die Änderungszeit auf die aktuelle lokale Zeit festgelegt. Andernfalls *Zeiten* muss auf eine Struktur vom Typ zeigen **_utimbuf**, definiert in SYS\UTIME. H.

Die **_utimbuf** -Struktur speichert die Datei und Zeiten von verwendeten **_utime** so ändern Sie die Datei-Änderungsdatum. Die Struktur enthält die folgenden Felder, die beide vom Typ **Time_t**:

| Feld |   |
|-------|---|
| **actime** | Uhrzeit des Dateizugriffs |
| **modtime** | Uhrzeit der Dateiänderung |

Bestimmte Versionen von der **_utimbuf** Struktur (**_utimebuf32** und **__utimbuf64**) werden mit der 32-Bit und 64-Bit-Versionen des Zeittyps definiert. Diese werden in den 32-Bit- und 64-Bit-spezifischen Versionen dieser Funktion verwendet. **_utimbuf** selbst verwendet standardmäßig einen 64-Bit-Zeittyp, sofern **_USE_32BIT_TIME_T** definiert ist.

**_utime** ist identisch mit **_futime** mit dem Unterschied, dass die *Filename* Argument **_utime** ist ein Dateiname oder ein Pfad zu einer Datei, anstatt einen Dateideskriptor, der ein Öffnen Sie die Datei.

**_wutime** ist eine Breitzeichen-Version von **_utime**; die *Filename* Argument **_wutime** ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tutime**|**_utime**|**_utime**|**_wutime**|
|**_tutime32**|**_utime32**|**_utime32**|**_wutime32**|
|**_tutime64**|**_utime64**|**_utime64**|**_wutime64**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderliche Header|Optionale Header|
|-------------|----------------------|----------------------|
|**_utime**, **_utime32**, **_utime64**|\<sys/utime.h>|\<errno.h>|
|**_utime64**|\<sys/utime.h>|\<errno.h>|
|**_wutime**|\<utime.h> oder \<wchar.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm verwendet **_utime** die dateiänderungszeit auf die aktuelle Uhrzeit festgelegt.

```C
// crt_utime.c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/utime.h>
#include <time.h>

int main( void )
{
   struct tm tma = {0}, tmm = {0};
   struct _utimbuf ut;

   // Fill out the accessed time structure
   tma.tm_hour = 12;
   tma.tm_isdst = 0;
   tma.tm_mday = 15;
   tma.tm_min = 0;
   tma.tm_mon = 0;
   tma.tm_sec = 0;
   tma.tm_year = 103;

   // Fill out the modified time structure
   tmm.tm_hour = 12;
   tmm.tm_isdst = 0;
   tmm.tm_mday = 15;
   tmm.tm_min = 0;
   tmm.tm_mon = 0;
   tmm.tm_sec = 0;
   tmm.tm_year = 102;

   // Convert tm to time_t
   ut.actime = mktime(&tma);
   ut.modtime = mktime(&tmm);

   // Show file time before and after
   system( "dir crt_utime.c" );
   if( _utime( "crt_utime.c", &ut ) == -1 )
      perror( "_utime failed\n" );
   else
      printf( "File time modified\n" );
   system( "dir crt_utime.c" );
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/09/2003  05:38 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
File time modified
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/15/2002  12:00 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[_futime, _futime32, _futime64](futime-futime32-futime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_stat- und _wstat-Funktionen](stat-functions.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
