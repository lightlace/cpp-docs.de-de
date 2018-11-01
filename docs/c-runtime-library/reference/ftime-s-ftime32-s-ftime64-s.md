---
title: _ftime_s, _ftime32_s, _ftime64_s
ms.date: 11/04/2016
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
ms.openlocfilehash: 696b461cdb6b8d58bb668b996a99c5d0bb774d6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435476"
---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s

Ruft die aktuelle Zeit ab Dies sind Versionen von [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT beschrieben](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Syntax

```C
errno_t _ftime_s( struct _timeb *timeptr );
errno_t _ftime32_s( struct __timeb32 *timeptr );
errno_t _ftime64_s( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Zeiger auf eine **_timeb**, **__timeb32**, oder **__timeb64** Struktur.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler. Wenn *Timeptr* ist **NULL**, der Rückgabewert ist **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_ftime_s** Funktion ruft die aktuelle Ortszeit ab und speichert sie in der Struktur verweist *Timeptr*. Die **_timeb**, **__timeb32**, und **__timeb64** Strukturen werden in sys\timeb definiert. Sie enthalten vier Felder, die in der folgenden Tabelle aufgeführt werden.

|Feld|Beschreibung|
|-|-|
|**dstflag**|Ein Wert ungleich null, wenn die Sommerzeit zurzeit für die lokale Zeitzone gültig ist. (Eine Erläuterung dazu, wie die Sommerzeit festgelegt wird, finden Sie unter [_tzset](tzset.md).)|
|**millitm**|Sekundenbruchteile in Millisekunden|
|**time**|Die Zeit in Sekunden seit dem 1. Januar 1970, Mitternacht (00: 00: 00) im UTC-Format|
|**Zeitzone**|Differenz in Minuten, westwärts zwischen UTC und der Ortszeit Der Wert des **Timezone** festgelegt ist, aus dem Wert der globalen Variablen **_timezone** (finden Sie unter **_tzset**).|

Die **_ftime64_s** -Funktion auf, die mithilfe der **__timeb64** Struktur, die Datumsangaben der dateierstellung bis 23:59:59, 31. Dezember 3000 UTC; ausgedrückt werden können, während **_ftime32_s** nur Datumsangaben bis 23:59:59 am 18. Januar 2038, UTC darstellt. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.

Die **_ftime_s** -Funktion ist gleichbedeutend mit **_ftime64_s**, und **_timeb** enthält einen 64-Bit-Uhrzeitwert, es sei denn, **_USE_32BIT_TIME_T** ist definiert, ist in diesem Fall das alte Verhalten wirksam. **_ftime_s** verwendet einen 32-Bit-Uhrzeitwert und **_timeb** enthält einen 32-Bit-Uhrzeitwert.

**_ftime_s** überprüft die eigenen Parameter. Wenn ein null-Zeiger als *Timeptr*, die Funktion ruft der Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Die Funktion legt fest, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** zu **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_ftime_s**|\<sys/types.h> und \<sys/timeb.h>|
|**_ftime32_s**|\<sys/types.h> und \<sys/timeb.h>|
|**_ftime64_s**|\<sys/types.h> und \<sys/timeb.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_ftime64_s.c
// This program uses _ftime64_s to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime64_s( &timebuffer );

    time1 = timebuffer.time;
    millitm1 = timebuffer.millitm;
    timezone1 = timebuffer.timezone;
    dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
