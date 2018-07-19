---
title: gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
dev_langs:
- C++
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b15896ff9ec96ed8dd9867c14d252edaad2c67a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405275"
---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

Konvertiert einen Zeitwert zu einem **tm** Struktur. Dies sind Versionen von [_gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md) mit Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
errno_t gmtime_s(
   struct tm* tmDest,
   const __time_t* sourceTime
);
errno_t _gmtime32_s(
   struct tm* tmDest,
   const __time32_t* sourceTime
);
errno_t _gmtime64_s(
   struct tm* tmDest,
   const __time64_t* sourceTime
);
```

### <a name="parameters"></a>Parameter

*tmDest*<br/>
Zeiger auf eine [tm](../../c-runtime-library/standard-types.md) Struktur. Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des der *Timer* -Arguments im UTC nicht in Ortszeit.

*sourceTime*<br/>
Zeiger auf die gespeicherte Zeit Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht (00:00: 00), verstrichen sind. Die Anzeige erfolgt im UTC-Format.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|*tmDest*|*sourceTime*|Zurück|Wert in *TmDest*|
|-----------|------------|------------|--------------------|
|**NULL**|alle|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (verweist auf gültige Speicher)|**NULL**|**EINVAL**|Alle Felder auf -1 festgelegt.|
|nicht **NULL**|< 0|**EINVAL**|Alle Felder auf -1 festgelegt.|

Im Fall der ersten zwei Fehlerbedingungen, wird der ungültige Parameterhandler aufgerufen, wie es unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_gmtime32_s** -Funktion gliedert den *SourceTime* Wert und speichert diesen in eine Struktur des Typs **tm**, die in Time.h definiert. Die Adresse der Struktur übergeben *TmDest*. Der Wert der *SourceTime* abgerufen wird normalerweise von einem Aufruf der [Zeit](time-time32-time64.md) Funktion.

> [!NOTE]
> Die Zielumgebung soll versuchen, zu bestimmen, ob die Sommerzeit wirksam ist. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit zu implementieren.

Jedes dieser Strukturfelder ist vom Typ **Int**, wie in der folgenden Tabelle gezeigt.

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
|**tm_isdst**|Immer 0 für **Gmtime_s**.|

**_gmtime64_s**, verwendet der **__time64_t** -Struktur, ermöglicht die Datumsangaben oben bis 23:59:59, 31. Dezember 3000, UTC; ausgedrückt werden, während **gmtime32_s** nur Datumsangaben bis zum darstellen 23:59:59 am 18. Januar 2038 UTC. Der 1. Januar 1970 (Mitternacht) ist der untere Datumsbereich für diese beiden Funktionen.

**Gmtime_s** ist eine Inlinefunktion, die ergibt **_gmtime64_s** und **Time_t** entspricht **__time64_t**. Wenn Sie den Compiler, interpretieren erzwingen müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**. Dadurch wird **Gmtime_s** eingebunden werden **_gmtime32_s**. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|---------------------|-|
|**gmtime_s**|, **_gmtime32_s**, **_gmtime64_s**|\<time.h>|\<CTime > oder \<time.h >|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_gmtime64_s.c
// This program uses _gmtime64_s to convert a 64-bit
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime_s to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm newtime;
   __int64 ltime;
   char buf[26];
   errno_t err;

   _time64( &ltime );

   // Obtain coordinated universal time:
   err = _gmtime64_s( &newtime, &ltime );
   if (err)
   {
      printf("Invalid Argument to _gmtime64_s.");
   }

   // Convert to an ASCII representation
   err = asctime_s(buf, 26, &newtime);
   if (err)
   {
      printf("Invalid Argument to asctime_s.");
   }

   printf( "Coordinated universal time is %s\n",
           buf );
}
```

```Output
Coordinated universal time is Fri Apr 25 20:12:33 2003
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
