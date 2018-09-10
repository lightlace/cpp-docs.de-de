---
title: _ftime, _ftime32, _ftime64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
dev_langs:
- C++
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8942dbaddcc1f4ab1ec5d571d08d95d8669d302d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107054"
---
# <a name="ftime-ftime32-ftime64"></a>_ftime, _ftime32, _ftime64

Ruft die aktuelle Zeit ab Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md).

## <a name="syntax"></a>Syntax

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Zeiger auf eine **_timeb**, **__timeb32**, oder **__timeb64** Struktur.

## <a name="remarks"></a>Hinweise

Die **_ftime** Funktion ruft die aktuelle Ortszeit ab und speichert sie in der Struktur verweist *Timeptr*. Die **_timeb**, **__timeb32**, und **__timeb64** in Strukturen definiert sind \<Sys\\timeb.h >. Sie enthalten vier Felder, die in der folgenden Tabelle aufgeführt werden.

|Feld|Beschreibung|
|-|-|
|**dstflag**|Ein Wert ungleich null, wenn die Sommerzeit zurzeit für die lokale Zeitzone gültig ist. (Eine Erläuterung dazu, wie die Sommerzeit festgelegt wird, finden Sie unter [_tzset](tzset.md).)|
|**millitm**|Sekundenbruchteile in Millisekunden|
|**time**|Die Zeit in Sekunden seit dem 1. Januar 1970, Mitternacht (00: 00: 00) im UTC-Format|
|**Zeitzone**|Differenz in Minuten, westwärts zwischen UTC und der Ortszeit Der Wert des **Timezone** festgelegt ist, aus dem Wert der globalen Variablen **_timezone** (finden Sie unter **_tzset**).|

Die **_ftime64** -Funktion auf, die mithilfe der **__timeb64** Struktur, die Datumsangaben der dateierstellung bis 23:59:59, 31. Dezember 3000 UTC; ausgedrückt werden können, während **_ftime32**nur Datumsangaben bis 23:59:59 am 18. Januar 2038, UTC darstellt. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.

Die **_ftime** -Funktion ist gleichbedeutend mit **_ftime64**, und **_timeb** enthält einen 64-Bit-Uhrzeitwert, es sei denn, **_USE_32BIT_TIME_T** definiert ist, in wobei das alte Verhalten ist wirksam. **_ftime** verwendet einen 32-Bit-Uhrzeitwert und **_timeb** enthält einen 32-Bit-Uhrzeitwert.

**_ftime** überprüft die eigenen Parameter. Wenn ein null-Zeiger als *Timeptr*, die Funktion ruft der Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Die Funktion legt fest, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** zu **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> und \<sys/timeb.h>|
|**_ftime32**|\<sys/types.h> und \<sys/timeb.h>|
|**_ftime64**|\<sys/types.h> und \<sys/timeb.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
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

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

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
