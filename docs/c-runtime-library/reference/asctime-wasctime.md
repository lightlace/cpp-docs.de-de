---
title: asctime, _wasctime | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
dev_langs:
- C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b18edc9e61f7065fcac1fe6231012bd232ccc18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396195"
---
# <a name="asctime-wasctime"></a>asctime, _wasctime

Konvertieren einer **tm** Zeit Struktur in eine Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

## <a name="syntax"></a>Syntax

```C
char *asctime(
   const struct tm *timeptr
);
wchar_t *_wasctime(
   const struct tm *timeptr
);
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Zeit-/Datumsstruktur.

## <a name="return-value"></a>Rückgabewert

**Asctime** gibt einen Zeiger auf das Ergebnis des Zeichens-Zeichenfolge. **_wasctime** gibt einen Zeiger auf das Ergebnis der Breitzeichen-Zeichenfolge zurück. Es gibt keinen Fehlerrückgabewert.

## <a name="remarks"></a>Hinweise

Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

Die **Asctime** Funktion konvertiert eine Zeit, die als eine Struktur in eine Zeichenfolge gespeichert. Die *Timeptr* Wert wird in der Regel von einem Aufruf abgerufen **Gmtime** oder **Localtime**, für die einen Zeiger auf Zurückgeben einer **tm** -Struktur in der Zeit definiert. H.

|timeptr.member|Wert|
|--------------------|-----------|
|**tm_hour**|Stunden seit Mitternacht (0-23)|
|**tm_isdst**|Positiv bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.|
|**tm_mday**|Tag des Monats (1-31)|
|**tm_min**|Minuten nach Stunde (0-59)|
|**tm_mon**|Monat (0-11; Januar = 0)|
|**tm_sec**|Sekunden nach Minute (0-59)|
|**tm_wday**|Tag der Woche (0-6; Sonntag = 0)|
|**tm_yday**|Tag des Jahres (0-365; 1. Januar = 0)|
|**tm_year**|Jahr (aktuelles Jahr minus 1900)|

Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der Zeitzonen finden Sie unter den [time](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md) und [localtime](localtime-localtime32-localtime64.md)-Funktionen. Informationen zur Definition der Zeitzonenumgebung und globalen Variablen finden Sie unter der [_tzset](tzset.md)-Funktion.

Das Zeichenfolgenergebnis von erzeugten **Asctime** enthält genau 26 Zeichen und hat die Form `Wed Jan 02 02:03:55 1980\n\0`. Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Die Zeilenwechsel- und Nullzeichen nehmen die letzten beiden Stellen der Zeichenfolge ein. **Asctime** verwendet einen einzelnen, statisch zugeordneten Puffer für die zurückgegebene Zeichenfolge. Jeder Aufruf dieser Funktion zerstört das Ergebnis des vorherigen Aufrufs.

**_wasctime** ist eine Breitzeichen-Version von **Asctime**. **_wasctime** und **Asctime** Verhalten sich andernfalls identisch.

Diese Funktionen überprüfen ihre Parameter. Wenn *Timeptr* ein null-Zeiger ist oder wenn er außerhalb des gültigen Bereichs Werte enthält, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **NULL** und legt **Errno** auf **EINVAL**.

### <a name="generic-text-routine-mapping"></a>Routinemäßige Allgemeintext-Zuordnung

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> oder \<wchar.h>|

## <a name="example"></a>Beispiel

Dieses Programm setzt die Systemzeit in langen ganzzahligen **Aclock**, übersetzt sie in der Struktur **Newtime** dann in Form einer Zeichenfolge für konvertiert, ausgeben, indem Sie die **Asctime**Funktion.

```C
// crt_asctime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
    struct tm   *newTime;
    time_t      szClock;

    // Get time in seconds
    time( &szClock );

    // Convert time to struct tm form
    newTime = localtime( &szClock );

    // Print local time as a string.
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996
    // Note: asctime is deprecated; consider using asctime_s instead
}
```

```Output
Current date and time: Sun Feb 03 11:38:58 2002
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
