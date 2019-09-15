---
title: _ftime, _ftime32, _ftime64
ms.date: 11/04/2016
api_name:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
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
ms.openlocfilehash: b8cc46a0a5470892e0bdfdcb0918c2757cdaf4c7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956336"
---
# <a name="_ftime-_ftime32-_ftime64"></a>_ftime, _ftime32, _ftime64

Ruft die aktuelle Zeit ab Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md).

## <a name="syntax"></a>Syntax

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Zeiger auf eine **_timeb**-, **__timeb32**-oder **__timeb64** -Struktur.

## <a name="remarks"></a>Hinweise

Die **_ftime** -Funktion Ruft die aktuelle Ortszeit ab und speichert Sie in der Struktur, auf die von *Timeptr*verwiesen wird. Die **_timeb**-, **__timeb32**-und **__timeb64** -Strukturen sind \<in\\der > sys timeb. h definiert. Sie enthalten vier Felder, die in der folgenden Tabelle aufgeführt werden.

|Feld|Beschreibung|
|-|-|
|**dstflag**|Ein Wert ungleich null, wenn die Sommerzeit zurzeit für die lokale Zeitzone gültig ist. (Eine Erläuterung dazu, wie die Sommerzeit festgelegt wird, finden Sie unter [_tzset](tzset.md).)|
|**millitm**|Sekundenbruchteile in Millisekunden|
|**time**|Die Zeit in Sekunden seit dem 1. Januar 1970, Mitternacht (00: 00: 00) im UTC-Format|
|**timezone**|Differenz in Minuten, westwärts zwischen UTC und der Ortszeit Der Wert von **Zeitzone** wird vom Wert der globalen Variablen **_timezone** festgelegt (siehe **_tzset**).|

Die **_ftime64** -Funktion, die die **__timeb64** -Struktur verwendet, ermöglicht das Ausdrücken von Dateierstellungs-Daten bis 23:59:59, 31. Dezember 3000, UTC; während **_ftime32** nur Datumsangaben 23:59:59 bis zum 18. Januar 2038 (UTC) darstellt. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.

Die **_ftime** -Funktion entspricht **_ftime64**, und **_timeb** enthält eine 64-Bit-Zeit, es sei denn, **_USE_32BIT_TIME_T** ist definiert. in diesem Fall ist das alte Verhalten wirksam. **_ftime** verwendet eine 32-Bit-Zeit, und **_timeb** enthält eine 32-Bit-Zeit.

**_ftime** überprüft seine Parameter. Wenn ein NULL-Zeiger als *Timeptr*übergeben wird, ruft die Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt die Funktion **errno** auf **EINVAL**fest.

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
