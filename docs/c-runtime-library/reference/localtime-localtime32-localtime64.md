---
title: localtime, _localtime32, _localtime64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs:
- C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32b462dfbe794d1817fa727736452e961a2b1dfd
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64

Konvertiert einen Zeitwert und berichtigt die lokale Zeitzone. Sicherere Versionen dieser Funktionen sind verfügbar. Diese finden Sie unter [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md).

## <a name="syntax"></a>Syntax

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parameter

*sourceTime*<br/>
Zeiger auf die gespeicherte Zeit

## <a name="return-value"></a>Rückgabewert

Geben Sie einen Zeiger auf das Ergebnis Struktur zurück oder **NULL** , wenn das Datum, an die Funktion übergeben wird:

- Vor Mitternacht, 1. Januar 1970

- Nach 03:14:07 am 19. Januar 2038 UTC (mit **_time32** und **time32_t**).

- Nach 23:59:59 am 31. Dezember 3000 UTC (mit **_time64** und **__time64_t**).

**_localtime64**, verwendet der **__time64_t** -Struktur, ermöglicht die Datumsangaben oben bis 23:59:59, 31. Dezember 3000, koordinierte Weltzeit (UTC) ausgedrückt werden, während **_localtime32** Stellt die Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC dar.

**LocalTime** ist eine Inlinefunktion, die ergibt **_localtime64**, und **Time_t** entspricht **__time64_t**. Wenn Sie den Compiler, interpretieren erzwingen müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**. Dadurch wird **Localtime** ausgewertet **_localtime32**. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.

Die Felder des Strukturtyps [tm](../../c-runtime-library/standard-types.md) speichern Sie die folgenden Werte an, von denen jedes eine **Int**:

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

## <a name="remarks"></a>Hinweise

Die **Localtime** -Funktion konvertiert eine Zeit gespeichert als eine [Time_t](../../c-runtime-library/standard-types.md) Wert und speichert das Ergebnis in einer Struktur vom Typ [tm](../../c-runtime-library/standard-types.md). Die **lange** Wert *SourceTime* stellt die Sekunden seit Mitternacht vergangenen (00: 00:00), 1. Januar 1970, UTC. Dieser Wert wird in der Regel abgerufen, von der [Zeit](time-time32-time64.md) Funktion.

Die 32-Bit und 64-Bit-Versionen von [Gmtime](gmtime-gmtime32-gmtime64.md), [Mktime](mktime-mktime32-mktime64.md), [Mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), und **Localtime** alle verwenden einen einzelnen **tm** Struktur pro Thread für die Konvertierung. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört.

**LocalTime** für die lokale Zeitzone korrigiert werden, wenn der Benutzer zunächst die globalen Umgebungsvariablen festgelegt **TZ**. Wenn **TZ** festgelegt wird, werden drei Umgebungsvariablen (**_timezone**, **_daylight**, und **_tzname**) werden ebenfalls automatisch festgelegt. Wenn die **TZ** Variable nicht festgelegt ist, **Localtime** versucht, die in der Datum/Uhrzeit-Anwendung in der Systemsteuerung festgelegten Zeitzonendaten zu verwenden. Wenn diese Information nicht abgerufen werden kann, wird standardmäßig PST8PDT verwendet, was die Zeitzone Pacific (PTC) darstellt. Unter [_tzset](tzset.md) finden Sie eine Beschreibung dieser Variablen. **TZ** ist eine Microsoft-Erweiterung und nicht Teil der standardmäßigen ANSI-Definition der **Localtime**.

> [!NOTE]
> Die Zielumgebung soll versuchen zu bestimmen, ob die Sommerzeit wirksam ist.

Diese Funktionen überprüfen ihre Parameter. Wenn *SourceTime* ein null-Zeiger ist oder wenn die *SourceTime* Wert negativ ist, rufen diese Funktionen einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, der Funktionen zurück **NULL** und **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|---------------------|-|
|**LocalTime**, **_localtime32**, **_localtime64**|\<time.h>|\<CTime > oder \<time.h >|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_localtime.cpp
// compile with: /W3
// This program uses _time64 to get the current time
// and then uses localtime64() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm *newtime;
    char am_pm[] = "AM";
    __time64_t long_time;

    _time64( &long_time );             // Get time as 64-bit integer.
                                       // Convert to local time.
    newtime = _localtime64( &long_time ); // C4996
    // Note: _localtime64 deprecated; consider _localetime64_s

    if( newtime->tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime->tm_hour > 12 )        // Convert from 24-hour
        newtime->tm_hour -= 12;        //   to 12-hour clock.
    if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime->tm_hour = 12;

    char buff[30];
    asctime_s( buff, sizeof(buff), newtime );
    printf( "%.19s %s\n", buff, am_pm );
}
```

```Output
Tue Feb 12 10:05:58 AM
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
