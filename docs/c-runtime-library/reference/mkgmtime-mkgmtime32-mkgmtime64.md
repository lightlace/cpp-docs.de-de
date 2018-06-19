---
title: _mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs:
- C++
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcb587cf5504f661512ccf88cf4f15d0555e2f18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405139"
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Konvertiert eine Zeit in UTC dargestellt durch eine **Struktur** **tm** in UTC-Zeit dargestellt, indem eine **Time_t** Typ.

## <a name="syntax"></a>Syntax

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>Parameter

*timeptr*<br/>
Ein Zeiger auf die UTC-Zeit, als eine **Struktur** **tm** konvertieren.

## <a name="return-value"></a>Rückgabewert

Eine Menge des Typs **__time32_t** oder **__time64_t** , der die Anzahl der Sekunden seit Mitternacht des 1. Januar 1970, in die koordinierte Weltzeit (UTC) verstrichen. Wenn das Datum außerhalb des gültigen Bereichs liegt (siehe Abschnitt "Hinweise") oder die Eingabe kann nicht als gültig interpretiert werden kann, wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **_mkgmtime32** und **_mkgmtime64** Funktionen konvertieren eine UTC-Zeit für eine **__time32_t** oder **__time64_t** Typ, der die Zeit in darstellt (UTC). Verwenden Sie zum Konvertieren einer Ortszeit in UTC-Zeit **Mktime**, **_mktime32**, und **_mktime64** stattdessen.

**_mkgmtime** ist eine Inlinefunktion, der ergibt **_mkgmtime64**, und **Time_t** entspricht **__time64_t**. Wenn Sie den Compiler, interpretieren erzwingen müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlagen (der maximalbereich von 32-Bit- **Time_t**), und es kann kein überhaupt auf 64-Bit-Plattformen.

Die Zeit, die Struktur übergeben werden wie folgt auf die gleiche Weise geändert werden, da sie mit geändert wurden die **_mktime** Funktionen: das **Tm_wday** und **Tm_yday** -Feld auf neu festgelegt werden Werte auf Grundlage der Werte der **Tm_mday** und **Tm_year**. Beim Angeben einer **tm** -strukturzeit, legen Sie die **Tm_isdst** -Feld hinzu:

- Null (0) weist darauf hin, dass die Normalzeit gilt.

- Ein Wert größer als 0 weist darauf hin, dass die Sommerzeit gilt.

- Ein Wert kleiner als null gibt an, dass der C-Laufzeitbibliothekscode berechnet, ob Normalzeit oder Sommerzeit gilt.

Die C-Laufzeitbibliothek verwendet die ZZ-Umgebungsvariable, um die richtige Sommerzeit zu bestimmen. Wurde keine ZZ festgelegt, wird das Betriebssystem abgefragt, um das richtige regionale Sommerzeitverhalten abzurufen. **Tm_isdst** ist ein Pflichtfeld. Wenn nicht festgelegt ist, dessen Wert nicht definiert ist und der Rückgabewert **Mktime** kann nicht berechnet werden.

Der Bereich von der **_mkgmtime32** Funktion wird von Mitternacht, 1. Januar 1970 UTC bis 23:59:59 dem 18. Januar 2038 UTC. Der Bereich von **_mkgmtime64** von Mitternacht, 1. Januar 1970 UTC bis 23:59:59 am 31. Dezember 3000 UTC ist. Ein Datum außerhalb des gültigen Bereichs führt ein Rückgabewert von – 1. Der Bereich von **_mkgmtime** davon abhängig, ob **_USE_32BIT_TIME_T** definiert ist. Wenn keine (Standard) definiert der Bereich ist, der **_mkgmtime64**ist, andernfalls der Bereich ist beschränkt auf den 32-Bit-Bereich des **_mkgmtime32**.

Beachten Sie, dass **Gmtime** und **Localtime** verwenden Sie einen einzelnen statisch zugeordneten Puffer für die Konvertierung. Wenn Sie diesen Puffer für angeben **Mkgmtime**, der vorherige Inhalt zerstört.

## <a name="example"></a>Beispiel

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

Das folgende Beispiel zeigt, wie die unvollständige Struktur mit den für den Tag der Woche und den Tag des Jahres berechneten Werten ausgefüllt wird.

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

### <a name="output"></a>Ausgabe

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
