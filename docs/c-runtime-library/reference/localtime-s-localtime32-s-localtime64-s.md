---
title: localtime_s, _localtime32_s, _localtime64_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1125f9a66a471b664e42ddbd5164611a4cb2ae69
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

Konvertiert eine **Time_t** Zeit-Wert, der eine **tm** Struktur, und für die lokale Zeitzone korrigiert. Dies sind Versionen von [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md) mit Sicherheitsverbesserungen wie in den [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t localtime_s(
   struct tm* tmDest,
   const time_t *sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   const time32_t *sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   const _time64_t *sourceTime
);
```

### <a name="parameters"></a>Parameter

*tmDest*<br/>
Ein Zeiger auf die Zeitstruktur, die ausgefüllt wird

*sourceTime*<br/>
Zeiger auf die gespeicherte Zeit.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|*tmDest*|*sourceTime*|Rückgabewert|Wert in *TmDest*|Ruft ungültige Parametertyphandler auf|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|alle|**EINVAL**|Nicht geändert|Ja|
|Nicht **NULL** (verweist auf gültige Speicher)|**NULL**|**EINVAL**|Alle Felder auf-1 festgelegt|Ja|
|Nicht **NULL** (verweist auf gültige Speicher)|kleiner als 0 oder größer als **_MAX__TIME64_T**|**EINVAL**|Alle Felder auf-1 festgelegt|Nein|

Im Fall der ersten zwei Fehlerbedingungen, wird der ungültige Parameterhandler aufgerufen, wie es unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_localtime32_s** -Funktion konvertiert eine Zeit gespeichert als eine [Time_t](../../c-runtime-library/standard-types.md) Wert und speichert das Ergebnis in einer Struktur vom Typ [tm](../../c-runtime-library/standard-types.md). Die **lange** Wert *SourceTime* stellt die Sekunden seit Mitternacht vergangenen (00: 00:00), 1. Januar 1970, UTC. Dieser Wert wird in der Regel abgerufen, von der [Zeit](time-time32-time64.md) Funktion.

**_localtime32_s** für die lokale Zeitzone korrigiert werden, wenn der Benutzer zunächst die globalen Umgebungsvariablen festgelegt **TZ**. Wenn **TZ** festgelegt wird, werden drei Umgebungsvariablen (**_timezone**, **_daylight**, und **_tzname**) werden ebenfalls automatisch festgelegt. Wenn die **TZ** Variable nicht festgelegt ist, **localtime32_s** versucht, die in der Datum/Uhrzeit-Anwendung in der Systemsteuerung festgelegten Zeitzonendaten zu verwenden. Wenn diese Information nicht abgerufen werden kann, wird standardmäßig PST8PDT verwendet, was die Zeitzone Pacific (PTC) darstellt. Unter [_tzset](tzset.md) finden Sie eine Beschreibung dieser Variablen. **TZ** ist eine Microsoft-Erweiterung und nicht Teil der standardmäßigen ANSI-Definition der **Localtime**.

> [!NOTE]
> Die Zielumgebung soll versuchen zu bestimmen, ob die Sommerzeit wirksam ist.

**_localtime64_s**, verwendet der **__time64_t** -Struktur, ermöglicht die Datumsangaben oben bis 23:59:59, dem 18. Januar 3001, koordinierte Weltzeit (UTC) ausgedrückt werden, während **_localtime32_s** Stellt die Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC dar.

**Localtime_s** ist eine Inlinefunktion, die ergibt **_localtime64_s**, und **Time_t** entspricht **__time64_t**. Wenn Sie den Compiler, interpretieren erzwingen müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**. Dadurch wird **Localtime_s** ausgewertet **_localtime32_s**. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.

Die Felder des Strukturtyps [tm](../../c-runtime-library/standard-types.md) speichern Sie die folgenden Werte an, von denen jedes eine **Int**.

|Feld|Beschreibung|
|-|-|
|**tm_sec**|Sekunden nach Minute (0 - 59).|
|**tm_min**|Minuten nach Stunde (0 - 59).|
|**tm_hour**|Stunden seit Mitternacht (0 - 23).|
|**tm_mday**|Tag des Monats (1-31).|
|**tm_mon**|Monat (0 - 11; Januar = 0).|
|**tm_year**|Jahr (aktuelles Jahr minus 1900).|
|**tm_wday**|Tag der Woche (0 - 6; Sonntag = 0).|
|**tm_yday**|Tag des Jahres (0 - 365; 1. Januar = 0).|
|**tm_isdst**|Positiver Wert bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit.|

Wenn die **TZ** -Umgebungsvariable festgelegt ist, wird der C-Laufzeitbibliothek geht davon aus Regeln, die den Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit (DST).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|---------------------|-|
|**Localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<CTime > oder \<time.h >|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
