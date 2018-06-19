---
title: mktime, _mktime32, _mktime64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
dev_langs:
- C++
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d02ae8e38a0d3e3b56b5ae69ddd937ef99d76b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405355"
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64

Konvertiert die Ortszeit in einen Kalenderwert.

## <a name="syntax"></a>Syntax

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Zeiger auf Zeitstruktur. Weitere Informationen finden Sie unter [asctime](asctime-wasctime.md).

## <a name="return-value"></a>Rückgabewert

**_mktime32** gibt die angegebene Kalenderzeit codiert als ein Wert vom Typ [Time_t](../../c-runtime-library/standard-types.md). Wenn *Timeptr* auf ein Datum vor Mitternacht, 1. Januar 1970 verweist oder wenn die Kalenderzeit nicht dargestellt werden kann, **_mktime32** gibt-1 zurück, die in den Typ umgewandelt **Time_t**. Bei Verwendung **_mktime32** und *Timeptr* Verweise ein Datum nach 23:59:59 am 18. Januar 2038 Coordinated Universal Time (UTC), es gibt-1 zurück, in den Typ umgewandelt **Time_t**.

**_mktime64** umgewandelt geben-1 zurück **__time64_t** Wenn *Timeptr* verweist auf ein Datum nach 23:59:59 am 31. Dezember 3000 UTC.

## <a name="remarks"></a>Hinweise

Die **Mktime**, **_mktime32** und **_mktime64** Funktionen konvertiert die angegebene Zeitstruktur (möglicherweise unvollständig) verweist, zu *Timeptr*in eine vollständig definierte Struktur mit normalisierten Werten und konvertiert Sie sie in einem **Time_t** kalenderzeitwert. Die konvertierte Zeit hat dieselbe Codierung wie die Werte, die von der Funktion [Uhrzeit](time-time32-time64.md) zurückgegeben wurden. Die ursprünglichen Werte eines der **Tm_wday** und **Tm_yday** Bestandteile der *Timeptr* -Struktur werden ignoriert, und die ursprünglichen Werte der anderen Komponenten sind nicht eingeschränkt normbereiche.

**Mktime** ist eine Inlinefunktion, die entspricht **_mktime64**, es sei denn, **_USE_32BIT_TIME_T** definiert ist, wird in diesem Fall entspricht Sie **_mktime32** .

Nach einer Anpassung auf UTC **_mktime32** behandelt Datumsangaben von Mitternacht, 1. Januar 1970 bis 23:59:59 am 18. Januar 2038 UTC. **_mktime64** behandelt Datumsangaben von Mitternacht, 1. Januar 1970 bis 23:59:59, 31. Dezember 3000. Diese Anpassung kann dazu führen, dass diese Funktionen-1 zurück (umgewandelt **Time_t**, **__time32_t** oder **__time64_t**), obwohl die von Ihnen angegebene Datum in Reichweite ist. Wenn Sie sich zum Beispiel im ägyptischen Kairo aufhalten, wo die Ortszeit zwei Stunden vor der UTC liegt, werden diese zwei Stunden zunächst von dem in *timeptr* angegebenen Datum abgezogen. Dadurch liegt das Datum nun möglicherweise außerhalb des zulässigen Bereichs.

Diese Funktionen können zum Überprüfen und Ausfüllen einer tm-Struktur verwendet werden. Wenn erfolgreich ist, legen Sie diese Funktionen die Werte der **Tm_wday** und **Tm_yday** je nach Bedarf, und legen Sie die anderen Komponenten auf die angegebene Kalenderzeit dargestellt, jedoch mit den erzwungenen Werten der normalen Bereiche. Der endgültige Wert der **Tm_mday** wird erst festgelegt, **Tm_mon** und **Tm_year** bestimmt werden. Beim Angeben einer **tm** -strukturzeit, legen Sie die **Tm_isdst** -Feld hinzu:

- Null (0) weist darauf hin, dass die Normalzeit gilt.

- Ein Wert größer als 0 weist darauf hin, dass die Sommerzeit gilt.

- Ein Wert kleiner als null gibt an, dass der C-Laufzeitbibliothekscode berechnet, ob Normalzeit oder Sommerzeit gilt.

Die C-Laufzeitbibliothek bestimmt das Sommerzeitverhalten anhand der [ZZ](tzset.md)-Umgebungsvariable. Wenn **TZ** nicht festgelegt ist, den Win32-API-Aufruf [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) wird verwendet, um die Sommerzeit Zeitinformationen vom Betriebssystem erhalten. Wenn dies fehlschlägt, geht die Bibliothek davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit angewendet werden. **Tm_isdst** ist ein Pflichtfeld. Wenn es nicht festgelegt wird, wird sein Wert nicht definiert und der Rückgabewert dieser Funktionen ist unvorhersehbar. Wenn *Timeptr* verweist auf eine **tm** Struktur, die von einem vorherigen Aufruf zurückgegebene [Asctime](asctime-wasctime.md), [Gmtime](gmtime-gmtime32-gmtime64.md), oder [Localtime](localtime-localtime32-localtime64.md) (oder Varianten dieser Funktionen), die **Tm_isdst** Feld enthält den richtigen Wert.

Beachten Sie, dass **Gmtime** und **Localtime** (und **_gmtime32**, **_gmtime64**, **_localtime32**, und **_localtime64**) verwenden Sie einen einzelnen Puffer pro Thread für die Konvertierung. Wenn Sie diesen Puffer für angeben **Mktime**, **_mktime32** oder **_mktime64**, der vorherige Inhalt zerstört.

Diese Funktionen überprüfen ihre Parameter. Handelt es sich bei *timeptr* um einen NULL-Zeiger, wird der ungültige Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben die Funktionen – 1 zurück und legen Sie **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
