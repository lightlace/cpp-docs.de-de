---
title: _futime, _futime32, _futime64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _futime64
- _futime32
- _futime
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
- futime
- _futime
- futime64
- _futime64
dev_langs:
- C++
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdd7b68ac9e3bf55f64b9a68f7b8075eab640faa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056819"
---
# <a name="futime-futime32-futime64"></a>_futime, _futime32, _futime64

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

*FILETIME-Element*<br/>
Zeiger auf die Struktur, die das neue Änderungsdatum enthält

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg 0 zurück. Wenn ein Fehler auftritt, wird der Handler für ungültige Parameter aufgerufen, so wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, gibt die Funktion-1 zurück und **Errno** nastaven NA hodnotu **EBADF**, der angibt, eines Ungültiger Dateideskriptor, oder **EINVAL**, der angibt, ein ungültiges der Parameter.

## <a name="remarks"></a>Hinweise

Die **_futime** Routine legt das Änderungsdatum und den Zeitpunkt des Zugriffs auf die geöffnete Datei zugeordneten *fd*. **_futime** ist identisch mit [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md), außer dass das Argument der Dateideskriptor einer geöffneten Datei und nicht den Namen einer Datei oder einen Pfad zu einer Datei. Die **_utimbuf** -Struktur enthält Felder für das neue Änderungsdatum und die Uhrzeit für den Zugriff. Beide Felder müssen gültige Werte enthalten. **_utimbuf32** und **_utimbuf64** sind identisch mit **_utimbuf** bzw. für die Verwendung der 32-Bit- und 64-Bit-Typen, mit Ausnahme. **_futime** und **_utimbuf** verwenden einen 64-Bit-Zeittyp und **_futime** ist, verhält sich genauso **_futime64**. Wenn Sie das alte Verhalten erzwingen möchten, definieren Sie **_USE_32BIT_TIME_T**. Dadurch wird **_futime** identisch Verhalten **_futime32** und bewirkt, dass die **_utimbuf** Struktur, die die 32-Bit-Zeittyp, somit entspricht verwendet **__utimbuf32**.

**_futime64**, verwendet der **__utimbuf64** Struktur können gelesen und Datumsangaben bis 23:59:59, 31. Dezember 3000 UTC; ändern, während ein Aufruf von **_futime32** schlägt fehl, wenn das Datum für die Datei ist nach 23:59:59 am 18. Januar 2038, UTC. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für diese Funktionen.

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

### <a name="input-crtfutimecinput"></a>Eingabe: crt_futime.c_input

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
