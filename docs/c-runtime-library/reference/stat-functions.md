---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
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
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
dev_langs:
- C++
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ce367bdee78be1610a36c887a04f2130375114
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418012"
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

Abrufen von Statusinformationen zu einer Datei.

## <a name="syntax"></a>Syntax

```C
int _stat(
   const char *path,
   struct _stat *buffer
);
int _stat32(
   const char *path,
   struct __stat32 *buffer
);
int _stat64(
   const char *path,
   struct __stat64 *buffer
);
int _stati64(
   const char *path,
   struct _stati64 *buffer
);
int _stat32i64(
   const char *path,
   struct _stat32i64 *buffer
);
int _stat64i32(
   const char *path,
   struct _stat64i32 *buffer
);
int _wstat(
   const wchar_t *path,
   struct _stat *buffer
);
int _wstat32(
   const wchar_t *path,
   struct __stat32 *buffer
);
int _wstat64(
   const wchar_t *path,
   struct __stat64 *buffer
);
int _wstati64(
   const wchar_t *path,
   struct _stati64 *buffer
);
int _wstat32i64(
   const wchar_t *path,
   struct _stat32i64 *buffer
);
int _wstat64i32(
   const wchar_t *path,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Pfad einer vorhandenen Datei oder eines vorhandenen Verzeichnisses enthält.

*buffer*<br/>
Ein Zeiger auf die Struktur, in der die Ergebnisse gespeichert werden.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt „0“ zurück, wenn die Dateistatusinformationen abgerufen werden. Ein Rückgabewert "-1" gibt einen Fehler an, in diesem Fall **Errno** festgelegt ist, um **ENOENT**, der angibt, dass der Dateiname oder Pfad nicht gefunden werden konnte. Ein Rückgabewert von **EINVAL** zeigt einen ungültigen Parameter; **Errno** auch **EINVAL** in diesem Fall.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

Der Datumsstempel einer Datei dargestellt werden kann, wird jedoch höher als Mitternacht, 1. Januar 1970 und vor 23:59:59, 31. Dezember 3000, UTC, es sei denn, Sie verwenden **_stat32** oder **_wstat32**, oder definiertes **_ USE_32BIT_TIME_T**, in diesem Fall das Datum nur bis 23:59:59 am 18. Januar 2038 UTC dargestellt werden kann.

## <a name="remarks"></a>Hinweise

Die **_stat** Funktion ruft Informationen über die Datei oder das Verzeichnis, die gemäß *Pfad* und speichert ihn in der Struktur verweist *Puffer*. **_stat** automatisch behandelt Multibyte-Zeichenfolgenargumente nach Bedarf, erkennen Multibyte-Zeichensequenzen entsprechend der multibyte-Codepage aktuell in Verwendung.

**_wstat** ist eine Breitzeichen-Version von **_stat**; das *Pfad* Argument **_wstat** ist eine Breitzeichen-Zeichenfolge. **_wstat** und **_stat** Verhalten sich identisch, außer dass **_wstat** verarbeitet keine Multibyte-Zeichenfolgen.

Varianten dieser Funktionen unterstützen 32-Bit- oder 64-Bit-Zeittypen und 32-Bit- oder 64-Bit-Dateilängen. Das erste numerische Suffix (**32** oder **64**) gibt die Größe der Zeit verwendet; das zweite Suffix ist entweder **i32** oder **i64**, der angibt, ob die Dateigröße als ganze 32-Bit oder 64-Bit-Zahl dargestellt wird.

**_stat** entspricht **_stat64i32**, und **Struktur** **_stat** enthält einen 64-Bit-Uhrzeitwert. Dies ist "true", wenn **_USE_32BIT_TIME_T** definiert ist, wird in diesem Fall wird das alte Verhalten wirksam; **_stat** verwendet eine 32-Bit-Zeit und **Struktur** **_stat** enthält einen 32-Bit-Uhrzeitwert. Dasselbe gilt für **_stati64**.

> [!NOTE]
> **_wstat** mit Windows Vista symbolischen Links nicht funktioniert. In diesen Fällen **_wstat** meldet immer eine Größe von 0. **_stat** funktioniert ordnungsgemäß mit symbolischen Verknüpfungen.

Diese Funktion überprüft ihre Parameter. Wenn entweder *Pfad* oder *Puffer* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat-Variationen des Uhrzeittyps und Dateilängentyps

|Funktionen|_USE_32BIT_TIME_T definiert?|Uhrzeittyp|Dateilängentyp|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|Nicht definiert|64-Bit|32-Bit|
|**_stat**, **_wstat**|Definiert|32-Bit|32-Bit|
|**_stat32**, **_wstat32**|Nicht von der Makrodefinition betroffen|32-Bit|32-Bit|
|**_stat64**, **_wstat64**|Nicht von der Makrodefinition betroffen|64-Bit|64-Bit|
|**_stati64**, **_wstati64**|Nicht definiert|64-Bit|64-Bit|
|**_stati64**, **_wstati64**|Definiert|32-Bit|64-Bit|
|**_stat32i64**, **_wstat32i64**|Nicht von der Makrodefinition betroffen|32-Bit|64-Bit|
|**_stat64i32**, **_wstat64i32**|Nicht von der Makrodefinition betroffen|64-Bit|32-Bit|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

Die **_stat** Struktur, die in SYS\STAT definiert. H, enthält die folgenden Felder.

|Feld||
|-|-|
**st_gid**|Numerischer Bezeichner der Gruppe, die die Datei besitzt (UNIX-spezifisch). Dieses Feld weist auf Windows-Systemen immer den Wert „0“ (null) auf. Eine umgeleitete Datei wird als Windows-Datei klassifiziert.
**st_atime**|Zeitpunkt des letzten Zugriffs auf die Datei. Gültig auf NTFS-, aber nicht auf FAT-formatierten Laufwerken.
**st_ctime**|Uhrzeit der Dateierstellung. Gültig auf NTFS-, aber nicht auf FAT-formatierten Laufwerken.
**st_dev**|Laufwerksnummer des Datenträgers, der die Datei enthält (wie **St_rdev**).
**st_ino**|Anzahl der Informationsknoten (der **Inode**) für die Datei (UNIX-spezifisch). In UNIX-Dateisystemen die **Inode** beschreibt die Datums- und Zeitstempel, Berechtigungen und Inhalt. Wenn Dateien feste miteinander verknüpft sind, verwenden sie dieselbe **Inode**. Die **Inode**, und daher **St_ino**, in den Dateisystemen FAT, HPFS oder NTFS ohne Bedeutung hat.
**st_mode**|Bitmaske für Dateimodusinformationen. Die **_S_IFDIR** Bit ist gesetzt, wenn *Pfad* gibt das Verzeichnis an; das **_S_IFREG** Bit ist gesetzt, wenn *Pfad* gibt eine gewöhnliche Datei oder ein Gerät. Lese-/Schreibbits für Benutzer werden entsprechend dem Berechtigungsmodus der Datei festgelegt; Ausführungsbits für Benutzer werden entsprechend der Dateierweiterung festgelegt.
**st_mtime**|Uhrzeit der letzten Änderung der Datei.
**st_nlink**|Bei Nicht-NTFS-Dateisystemen immer „1“.
**st_rdev**|Laufwerksnummer des Datenträgers, der die Datei enthält (wie **St_dev**).
**st_size**|Die Größe der Datei in Bytes. eine ganze 64-Bit-Zahl für Varianten mit der **i64** Suffix.
**st_uid**|Numerischer Bezeichner des Benutzers, der die Datei besitzt (UNIX-spezifisch). Dieses Feld hat bei Windows-Systemen immer den Wert „0“. Eine umgeleitete Datei wird als Windows-Datei klassifiziert.

Wenn *Pfad* bezieht sich auf einem Gerät die **St_size**, verschiedenen Zeitfelder, **St_dev**, und **St_rdev** Felder in der **_stat**  Struktur sind bedeutungslos. Da „STAT.H“ den [_dev_t](../../c-runtime-library/standard-types.md) -Typ verwendet, der in „TYPES.H“ definiert ist, müssen Sie „TYPES.H“ vor „STAT.H“ in Ihrem Code einschließen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/types.h> gefolgt von \<sys/stat.h>|\<errno.h>|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64**, **_wstat32i64**, **_wstat64i32**|\<sys/types.h> gefolgt von \<sys/stat.h> oder \<wchar.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_stat.c
// This program uses the _stat function to
// report information about the file named crt_stat.c.

#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
   struct _stat buf;
   int result;
   char timebuf[26];
   char* filename = "crt_stat.c";
   errno_t err;

   // Get data associated with "crt_stat.c":
   result = _stat( filename, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      perror( "Problem getting information" );
      switch (errno)
      {
         case ENOENT:
           printf("File %s not found.\n", filename);
           break;
         case EINVAL:
           printf("Invalid parameter to _stat.\n");
           break;
         default:
           /* Should never be reached. */
           printf("Unexpected error in _stat.\n");
      }
   }
   else
   {
      // Output some of the statistics:
      printf( "File size     : %ld\n", buf.st_size );
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid arguments to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
}
```

```Output
File size     : 732
Drive         : C:
Time modified : Thu Feb 07 14:39:36 2002
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
