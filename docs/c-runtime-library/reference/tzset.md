---
title: _tzset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _tzset
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
- _tzset
dev_langs:
- C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15464ac8be075d44a9a42223964239538508a683
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417375"
---
# <a name="tzset"></a>_tzset

Legt die Umgebungsvariablen für die Zeit fest.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
void _tzset( void );
```

## <a name="remarks"></a>Hinweise

Die **_tzset** -Funktion verwendet die aktuelle Einstellung der Umgebungsvariablen **TZ** , Werte zu drei globalen Variablen zuzuweisen: **_daylight**, **_timezone** , und **_tzname**. Diese Variablen werden verwendet, durch die [_ftime](ftime-ftime32-ftime64.md) und [Localtime](localtime-localtime32-localtime64.md) Funktionen, um Korrekturen von der koordinierten Weltzeit (UTC) in die Ortszeit, und machen die [Zeit](time-time32-time64.md) -Funktion Berechnen Sie UTC aus der Systemzeit zu. Verwenden Sie die folgende Syntax zum Festlegen der **TZ** -Umgebungsvariablen angegeben:

> **Legen Sie TZ =**_Tzn_ \[ **+** &#124; **-**]*"hh"* \[ **:**_mm_\[**:**_ss_]] [*Dzn*]

|Parameter|Beschreibung|
|-|-|
*tzn*|Dreibuchstabiger Zeitzonenname, z. B. PST. Sie müssen die richtige Verschiebung (Offset) von der Ortszeit zur UTC angeben.
*hh*|Unterschied in Stunden zwischen UTC und Ortszeit. Das Pluszeichen (+) ist für positive Werte optional.
*mm*|Minuten. Von getrennt *"hh"* durch einen Doppelpunkt (**:**).
*ss*|Sekunden. Von getrennt *mm* durch einen Doppelpunkt (**:**).
*dzn*|Dreibuchstabige Sommerzeitzone, z. B. PDT. Wenn die Sommerzeit gültig nie Ort ist, legen **TZ** ohne einen Wert für *Dzn*. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.

> [!NOTE]
> Seien Sie vorsichtig, wenn Sie das Zeichen des Zeitunterschieds berechnen. Da der Zeitunterschied die Verschiebung von der Ortszeit zu UTC (anstatt umgekehrt) ist, ist das dazugehörige Zeichen gegenüber dem erwarteten möglicherweise das entgegengesetzte. Für Zeitzonen vor UTC ist der Zeitunterschied negativ; für Zeitzonen hinter UTC ist der Unterschied positiv.

Z. B. zum Festlegen der **TZ** -Umgebungsvariable auf der aktuellen Zeitzone in Deutschland Geben Sie Folgendes in der Befehlszeile:

> **Legen Sie TZ = GST 1GDT**

Dieser Befehl verwendet GST zur Angabe der deutschen Normalzeit und setzt voraus, dass UTC eine Stunde hinter Deutschland (oder Deutschland eine Stunde vor UTC) ist, und dass Deutschland die Sommerzeit berücksichtigt.

Wenn die **TZ** Wert nicht festgelegt ist, **_tzset** versucht, die vom Betriebssystem festgelegten Zeitzonendaten zu verwenden. Im Windows-Betriebssystem werden diese Informationen in der Datum/Uhrzeit-Anwendung in der Systemsteuerung angegeben. Wenn **_tzset** kann nicht abgerufen werden diese Informationen werden standardmäßig die Pacific Time Zeitzone PST8PDT verwendet.

Auf der Grundlage der **TZ** umgebungsvariablenwert, werden die folgenden Werte den globalen Variablen zugewiesen **_daylight**, **_timezone**, und **_tzname** Wenn **_tzset** aufgerufen wird:

|Globale Variable|Beschreibung|Standardwert|
|---------------------|-----------------|-------------------|
|**_daylight**|Wert ungleich NULL, wenn in eine Zone Sommerzeit angegeben ist **TZ** festlegen; andernfalls 0.|1|
|**_timezone**|Unterschied in Sekunden zwischen Ortszeit und UTC.|28800 (28800 Sekunden sind gleich 8 Stunden)|
|**_tzname**[0]|Zeichenfolgenwert des Zeitzonennamens aus **TZ** Umgebungsvariablen; leer, wenn **TZ** wurde nicht festgelegt.|PST|
|**_tzname**[1]|Der Zeichenfolgenwert der Sommerzeitzone; leer, wenn die Sommerzeitzone-weggelassen wurde **TZ** Umgebungsvariable.|PDT|

In der vorherigen Tabelle aufgeführten Standardwerte **_daylight** und **_tzname** Array entsprechen "PST8PDT." Wenn die DST-Zone im ausgelassen wird die **TZ** Umgebungsvariable, die den Wert der **_daylight** ist 0 und der [_ftime](ftime-ftime32-ftime64.md), [Gmtime](gmtime-gmtime32-gmtime64.md), und [Localtime](localtime-localtime32-localtime64.md) Funktionen für ihre jeweiligen DST-Flags 0 zurück.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_tzset**|\<time.h>|

Die **_tzset** Funktion ist die Microsoft-spezifische. Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_tzset.cpp
// This program uses _tzset to set the global variables
// named _daylight, _timezone, and _tzname. Since TZ is
// not being explicitly set, it uses the system time.

#include <time.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    _tzset();
    int daylight;
    _get_daylight( &daylight );
    printf( "_daylight = %d\n", daylight );
    long timezone;
    _get_timezone( &timezone );
    printf( "_timezone = %ld\n", timezone );
    size_t s;
    char tzname[100];
    _get_tzname( &s, tzname, sizeof(tzname), 0 );
    printf( "_tzname[0] = %s\n", tzname );
    exit( 0 );
}
```

```Output
_daylight = 1
_timezone = 28800
_tzname[0] = Pacific Standard Time
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
