---
title: gmtime, _gmtime32, _gmtime64
ms.date: 11/04/2016
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: 4f32da5920a0cb892619195207d6501a4b1fd874
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480001"
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

Konvertiert eine **Time_t** Zeit-Wert, der eine **tm** Struktur. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Syntax

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parameter

*sourceTime*<br/>
Zeiger auf die gespeicherte Zeit. Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht (00:00: 00), verstrichen sind. Die Anzeige erfolgt im UTC-Format.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Struktur des Typs [tm](../../c-runtime-library/standard-types.md). Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des der *SourceTime* Argument in UTC, anstatt in Ortszeit. Jedes Strukturfeld ist vom Typ **Int**wie folgt:

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
|**tm_isdst**|Immer 0 für **Gmtime**.|

Die 32-Bit und 64-Bit-Versionen der **Gmtime**, [Mktime](mktime-mktime32-mktime64.md), [Mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), und [Localtime](localtime-localtime32-localtime64.md) alle verwenden eine gemeinsame **tm**  Struktur für die Konvertierung pro Thread. Jeder Aufruf dieser Funktionen zerstört das Ergebnis des vorherigen Aufrufs. Wenn *SourceTime* stellt ein Datum vor Mitternacht, 1. Januar 1970 **Gmtime** gibt **NULL**. Es gibt keine Fehlerrückgabe.

**_gmtime64**, verwendet der **__time64_t** Struktur, die Datumsangaben bis 23:59:59, 31. Dezember 3000 UTC ausgedrückt werden können, während **_gmtime32** nur Datumsangaben bis 23:59:59 Uhr darstellen Am 18. Januar 2038, UTC. Der 1. Januar 1970 (Mitternacht) ist der untere Datumsbereich für beide Funktionen.

**Gmtime** ist eine Inlinefunktion, die ergibt **_gmtime64**, und **Time_t** entspricht **__time64_t** , wenn **_USE_32BIT_TIME_ T** definiert ist. Wenn Sie den Compiler, interpretieren erzwingen müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**, aber dazu **Gmtime** eingebunden sein **_gmtime32** und **Time_t** als definiert werden **__time32_t**. Diese Aktion sollte nicht durchgeführt werden, da sie auf 64-Bit-Plattformen nicht zugelassen ist und die Anwendung auf jedem Fall nach dem 18. Januar 2038 fehlschlägt.

Diese Funktionen überprüfen ihre Parameter. Wenn *SourceTime* ein null-Zeiger ist oder wenn die *SourceTime* Wert negativ ist, rufen diese Funktionen einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen geben **NULL** und **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_gmtime32** -Funktion gliedert den *SourceTime* -Wert und speichert diesen in eine statistisch zugeordnete Struktur vom Typ **tm**rechtzeitig definiert. H. Der Wert des *SourceTime* normalerweise erhalten Sie von einem Aufruf der [Zeit](time-time32-time64.md) Funktion.

> [!NOTE]
> In den meisten Fällen versucht die Zielumgebung zu bestimmen, ob die Sommerzeit wirksam ist. Die C-Laufzeitbibliothek geht davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit (DST, Daylight Saving Time) angewendet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|---------------------|-|
|**Gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<CTime > oder \<time.h >|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
