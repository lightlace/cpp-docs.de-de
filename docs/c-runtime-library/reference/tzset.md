---
title: _tzset
ms.date: 11/04/2016
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
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: 6312297e6daa9b4790674bd26d21812d5bee34c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385192"
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

Die **_tzset** -Funktion verwendet die aktuelle Einstellung der Umgebungsvariablen **TZ** drei globalen Variablen Werte zuweisen: **_daylight**, **_timezone** , und **_tzname**. Diese Variablen werden verwendet, durch die [_ftime](ftime-ftime32-ftime64.md) und [Localtime](localtime-localtime32-localtime64.md) Funktionen, um Korrekturen von der koordinierten Weltzeit (UTC) in die lokale Zeit, und machen die [Zeit](time-time32-time64.md) -Funktion Compute-UTC aus der Systemzeit. Verwenden Sie die folgende Syntax zum Festlegen der **TZ** -Umgebungsvariablen angegeben:

> **set TZ=**_tzn_ \[**+**&#124;**-**]*hh*\[**:**_mm_\[**:**_ss_] ][*dzn*]

|Parameter|Beschreibung|
|-|-|
| *tzn* | Dreibuchstabiger Zeitzonenname, z. B. PST. Sie müssen die richtige Verschiebung (Offset) von der Ortszeit zur UTC angeben. |
| *hh* | Unterschied in Stunden zwischen UTC und Ortszeit. Das Pluszeichen (+) ist für positive Werte optional. |
| *mm* | Minuten. Von getrennt *Hh* durch einen Doppelpunkt (**:**). |
| *ss* | Sekunden. Von getrennt *mm* durch einen Doppelpunkt (**:**). |
| *dzn* | Dreibuchstabige Sommerzeitzone, z. B. PDT. Wenn Sommerzeit nie aktiviert am Ort ist, legen Sie **TZ** ohne einen Wert für *Dzn*. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren. |

> [!NOTE]
> Seien Sie vorsichtig, wenn Sie das Zeichen des Zeitunterschieds berechnen. Da der Zeitunterschied die Verschiebung von der Ortszeit zu UTC (anstatt umgekehrt) ist, ist das dazugehörige Zeichen gegenüber dem erwarteten möglicherweise das entgegengesetzte. Für Zeitzonen vor UTC ist der Zeitunterschied negativ; für Zeitzonen hinter UTC ist der Unterschied positiv.

Beispielsweise, um das Festlegen der **TZ** Umgebungsvariable entsprechen der aktuellen Zeitzone in Deutschland, geben Sie Folgendes in der Befehlszeile:

> **set TZ=GST-1GDT**

Dieser Befehl verwendet GST zur Angabe der deutschen Normalzeit und setzt voraus, dass UTC eine Stunde hinter Deutschland (oder Deutschland eine Stunde vor UTC) ist, und dass Deutschland die Sommerzeit berücksichtigt.

Wenn die **TZ** Wert nicht festgelegt ist, **_tzset** versucht, die vom Betriebssystem festgelegten Zeitzonendaten zu verwenden. Im Windows-Betriebssystem werden diese Informationen in der Datum/Uhrzeit-Anwendung in der Systemsteuerung angegeben. Wenn **_tzset** dieser Informationen kann nicht abgerufen werden. standardmäßig die pazifischen Zeitzone gibt PST8PDT verwendet.

Auf der Grundlage der **TZ** umgebungsvariablenwert, werden die folgenden Werte an die globalen Variablen zugewiesen **_daylight**, **_timezone**, und **_tzname** beim **_tzset** aufgerufen wird:

|Globale Variable|Beschreibung|Standardwert|
|---------------------|-----------------|-------------------|
|**_daylight**|Wert ungleich NULL, wenn eine Zone Sommer-/ Winterzeit in angegeben ist **TZ** festlegen; andernfalls 0.|1|
|**_timezone**|Unterschied in Sekunden zwischen Ortszeit und UTC.|28800 (28800 Sekunden sind gleich 8 Stunden)|
|**_tzname**[0]|String-Wert, der Name der Zeitzone von **TZ** Umgebungsvariablen; leer, wenn **TZ** nicht festgelegt wurde.|PST|
|**_tzname**[1]|Der Zeichenfolgenwert der Sommerzeitzone; leer, wenn die Sommerzeitzone-in fehlt **TZ** Umgebungsvariable.|PDT|

In der obigen Tabelle aufgeführten Standardwerte **_daylight** und **_tzname** Array entsprechen "PST8PDT." Wenn die DST-Zone in fehlt die **TZ** -Umgebungsvariable wird der Wert des **_daylight** ist 0 und der [_ftime](ftime-ftime32-ftime64.md), [Gmtime](gmtime-gmtime32-gmtime64.md), und [Localtime](localtime-localtime32-localtime64.md) Funktionen geben für ihre jeweiligen DST-Flags 0 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_tzset**|\<time.h>|

Die **_tzset** Funktion ist die Microsoft-spezifisch. Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
