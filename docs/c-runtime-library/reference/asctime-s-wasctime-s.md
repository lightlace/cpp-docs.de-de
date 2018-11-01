---
title: asctime_s, _wasctime_s
ms.date: 11/04/2016
apiname:
- _wasctime_s
- asctime_s
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
- asctime_s
- _wasctime_s
- _tasctime_s
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
ms.openlocfilehash: 350d8c7b1dcf61272a3cfee884dff8a63b455f1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471954"
---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s

Konvertieren einer **tm** -Zeitstruktur in einer Zeichenfolge. Diese Funktionen sind Versionen von [asctime, _wasctime](asctime-wasctime.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen](../../c-runtime-library/security-features-in-the-crt.md) in der CRT beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t asctime_s(
   char* buffer,
   size_t numberOfElements,
   const struct tm *tmSource
);
errno_t _wasctime_s(
   wchar_t* buffer,
   size_t numberOfElements
   const struct tm *tmSource
);
template <size_t size>
errno_t asctime_s(
   char (&buffer)[size],
   const struct tm *tmSource
); // C++ only
template <size_t size>
errno_t _wasctime_s(
   wchar_t (&buffer)[size],
   const struct tm *tmSource
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Ein Zeiger auf einen Puffer, um das Zeichenfolgenergebnis zu speichern. Diese Funktion nimmt einen Zeiger auf einen gültigen Speicherbereich mit einer Größe von angegebenen *NumberOfElements*.

*numberOfElements*<br/>
Die Größe des Puffers zum Speichern des Ergebnisses verwendet werden soll.

*tmSource*<br/>
Zeit-/Datumsstruktur. Diese Funktion nimmt einen Zeiger auf ein gültiges **Struktur** **tm** Objekt.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Wenn es einen Fehler gibt, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, ist der Rückgabewert ein Fehlercode. Fehlercodes sind in ERRNO.H definiert. Weitere Informationen finden Sie unter [errno-Konstanten](../../c-runtime-library/errno-constants.md). Die jeweiligen Fehlercodes, die für jede Fehlerbedingung zurückgegeben werden, sind in folgender Tabelle aufgelistet.

### <a name="error-conditions"></a>Fehlerbedingungen

|*buffer*|*numberOfElements*|*tmSource*|Zurück|Wert in *Puffer*|
|--------------|------------------------|----------|------------|-----------------------|
|**NULL**|Beliebig|Beliebig|**EINVAL**|Nicht geändert|
|Nicht **NULL** (zeigt auf gültigen Speicher)|0|Beliebig|**EINVAL**|Nicht geändert|
|Nicht **NULL**|0< Größe < 26|Beliebig|**EINVAL**|Leere Zeichenfolge|
|Nicht **NULL**|>= 26|**NULL**|**EINVAL**|Leere Zeichenfolge|
|Nicht **NULL**|>= 26|Ungültige Zeitstruktur oder Zeitkomponentenwerte außerhalb des Bereichs|**EINVAL**|Leere Zeichenfolge|

> [!NOTE]
> Fehlerbedingungen für **Wasctime_s** ähneln **Asctime_s** mit der Ausnahme, dass die maximale Größe in Wörtern angegeben wird.

## <a name="remarks"></a>Hinweise

Die **Asctime** -Funktion konvertiert eine Zeit, die als eine Struktur in eine Zeichenfolge gespeichert. Die *TmSource* Wert wird in der Regel von einem Aufruf abgerufen **Gmtime** oder **Localtime**. Beide Funktionen können verwendet werden, um das Füllen einer **tm** Struktur, wie in der Zeit definiert. H.

|timeptr.member|Wert|
|--------------------|-----------|
|**tm_hour**|Stunden seit Mitternacht (0-23)|
|**tm_isdst**|Positiv bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.|
|**tm_mday**|Tag des Monats (1-31)|
|**tm_min**|Minuten nach Stunde (0-59)|
|**tm_mon**|Monat (0 – 11; Januar = 0)|
|**tm_sec**|Sekunden nach Minute (0-59)|
|**tm_wday**|Tag der Woche (0-6; Sonntag = 0)|
|**tm_yday**|Tag des Jahres (0 – 365; 1. Januar = 0)|
|**tm_year**|Jahr (aktuelles Jahr minus 1900)|

Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der Zeitzonen finden Sie unter den [time, _time32, _time64](time-time32-time64.md), [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) und [localtime_s, _localtime32_s, _localtime64_2](localtime-s-localtime32-s-localtime64-s.md)-Funktionen. Informationen zur Definition der Zeitzonenumgebung und globalen Variablen finden Sie unter der [_tzset](tzset.md)-Funktion.

Das Zeichenfolgenergebnis erzeugten **Asctime_s** enthält genau 26 Zeichen und weist das Format `Wed Jan 02 02:03:55 1980\n\0`. Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Die Zeilenwechsel- und Nullzeichen nehmen die letzten beiden Stellen der Zeichenfolge ein. Der Wert, der als zweiter Parameter übergeben wird, sollte mindestens so hoch sein. Ist dies weniger, einen Fehlercode und **EINVAL**, zurückgegeben werden.

**_wasctime_s** ist eine Breitzeichen-Version von **Asctime_s**. **_wasctime_s** und **Asctime_s** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mapping"></a>Routinemäßige Allgemeintext-Zuordnung

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladung](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**asctime_s**|\<time.h>|
|**_wasctime_s**|\<time.h> oder \<wchar.h>|

## <a name="security"></a>Sicherheit

Zeiger auf den Puffer ist nicht **NULL** und der Zeiger nicht auf einen gültigen Puffer, die Funktion überschreibt alle an der Position befindet. Dies kann auch zu einer Zugriffsverletzung führen.

Wenn das übergebene Größenargument größer als die tatsächliche Puffergröße ist, kann ein [Pufferüberlauf](/windows/desktop/SecBP/avoiding-buffer-overruns) auftreten.

## <a name="example"></a>Beispiel

Dieses Programm platziert die Systemzeit in der lange ganze Zahl **Aclock**, übersetzt sie in der Struktur **Newtime** und dann in Form einer Zeichenfolge für die Ausgabe, indem konvertiert die **Asctime_s**Funktion.

```C
// crt_asctime_s.c
#include <time.h>
#include <stdio.h>

struct tm newtime;
__time32_t aclock;

int main( void )
{
   char buffer[32];
   errno_t errNum;
   _time32( &aclock );   // Get time in seconds.
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.

   // Print local time as a string.

   errNum = asctime_s(buffer, 32, &newtime);
   if (errNum)
   {
       printf("Error code: %d", (int)errNum);
       return 1;
   }
   printf( "Current date and time: %s", buffer );
   return 0;
}
```

```Output
Current date and time: Wed May 14 15:30:17 2003
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
