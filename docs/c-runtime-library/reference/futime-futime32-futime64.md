---
title: _futime, _futime32, _futime64
ms.date: 11/04/2016
api_name:
- _futime64
- _futime32
- _futime
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 3de638f08882e2aae4743311730afcd888c43a60
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956236"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

Legt das Änderungsdatum einer offenen Datei fest

## <a name="syntax"></a>Syntax

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor der geöffneten Datei

*filetime*<br/>
Zeiger auf die Struktur, die das neue Änderungsdatum enthält

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg 0 zurück. Wenn ein Fehler auftritt, wird der Handler für ungültige Parameter aufgerufen, so wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion-1 zurück, und **errno** ist auf **EBADF**festgelegt, was einen ungültigen Dateideskriptor angibt, oder **EINVAL**, der einen ungültigen Parameter angibt.

## <a name="remarks"></a>Hinweise

Mit der **_futime** -Routine werden das Änderungsdatum und die Zugriffszeit in der geöffneten Datei, die mit *FD*verknüpft ist, festgelegt. **_futime** ist mit [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)identisch, mit der Ausnahme, dass das-Argument der Dateideskriptor einer geöffneten Datei und nicht der Name einer Datei oder ein Pfad zu einer Datei ist. Die **_utimbuf** -Struktur enthält Felder für das neue Änderungsdatum und die Zugriffszeit. Beide Felder müssen gültige Werte enthalten. **_utimbuf32** und **_utimbuf64** sind mit **_utimbuf** identisch, mit Ausnahme der Verwendung der 32-Bit-und 64-Bit-Uhrzeittypen. **_futime** und **_utimbuf** verwenden einen 64-Bit-Uhrzeittyp, und **_futime** ist im Verhalten von **_futime64**identisch. Wenn Sie das alte Verhalten erzwingen müssen, definieren Sie **_USE_32BIT_TIME_T**. Dies bewirkt, dass **_futime** identisch mit **_futime32** ist, und bewirkt, dass die **_utimbuf** -Struktur den 32-Bit-Uhrzeittyp verwendet, wodurch Sie **__utimbuf32**entspricht.

**_futime64**, das die **__utimbuf64** -Struktur verwendet, kann Datumsangaben bis 23:59:59 Uhr, 31. Dezember 3000, UTC, lesen und ändern. während ein **_futime32** -Aufrufvorgang fehlschlägt, wenn das Datum der Datei nach dem 18. Januar 2038 UTC 23:59:59 liegt. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für diese Funktionen.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionaler Header|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>Eingabe: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
