---
title: _tzset | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _tzset
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
f1_keywords: _tzset
dev_langs: C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f103da7ca67721f6c654c593746b9427954c6930
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tzset"></a>_tzset
Legt die Umgebungsvariablen für die Zeit fest.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter                  [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `_tzset` -Funktion verwendet die aktuelle Einstellung der Umgebungsvariablen `TZ` , um Werte zu drei globalen Variablen zuzuweisen: `_daylight`, `_timezone`und `_tzname`. Diese Variablen werden von den Funktionen [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) verwendet, um Korrekturen von der koordinierten Weltzeit (UTC) zur Ortszeit zu unterstützen, und von der Funktion `time` , um die UTC aus der Systemzeit zu ermitteln. Verwenden Sie zum Festlegen der `TZ` -Umgebungsvariable die folgende Syntax:  
  
 `set` `TZ`=`tzn`[+ &#124; -]`hh`[`:mm`[`:ss`] ][`dzn`]  
  
 `tzn`  
 Dreibuchstabiger Zeitzonenname, z. B. PST. Sie müssen die richtige Verschiebung (Offset) von der Ortszeit zur UTC angeben.  
  
 `hh`  
 Unterschied in Stunden zwischen UTC und Ortszeit. Das Pluszeichen (+) ist für positive Werte optional.  
  
 `mm`  
 Minuten. Von `hh` durch einen Doppelpunkt (`:`) getrennt.  
  
 `ss`  
 Sekunden. Von `mm` durch einen Doppelpunkt (`:`) getrennt.  
  
 `dzn`  
 Dreibuchstabige Sommerzeitzone, z. B. PDT. Wenn es am Ort keine Sommerzeit gibt, legen Sie `TZ` ohne einen Wert für `dzn`fest. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.  
  
> [!NOTE]
>  Seien Sie vorsichtig, wenn Sie das Zeichen des Zeitunterschieds berechnen. Da der Zeitunterschied die Verschiebung von der Ortszeit zu UTC (anstatt umgekehrt) ist, ist das dazugehörige Zeichen gegenüber dem erwarteten möglicherweise das entgegengesetzte. Für Zeitzonen vor UTC ist der Zeitunterschied negativ; für Zeitzonen hinter UTC ist der Unterschied positiv.  
  
 Um beispielsweise die `TZ` -Umgebungsvariable entsprechend der aktuellen Zeitzone in Deutschland festzulegen, geben Sie in die Befehlszeile Folgendes ein:  
  
```  
set TZ=GST-1GDT  
```  
  
 Dieser Befehl verwendet GST zur Angabe der deutschen Normalzeit und setzt voraus, dass UTC eine Stunde hinter Deutschland (oder Deutschland eine Stunde vor UTC) ist, und dass Deutschland die Sommerzeit berücksichtigt.  
  
 Wenn die `TZ` Wert nicht festgelegt ist, `_tzset` versucht, die vom Betriebssystem festgelegten Zeitzonendaten zu verwenden. Im Windows-Betriebssystem werden diese Informationen in der Datum/Uhrzeit-Anwendung in der Systemsteuerung angegeben. Wenn `_tzset` diese Informationen nicht abrufen kann, wird standardmäßig die Zeitzone PST8PDT (Pacific Time) verwendet.  
  
 Je nach dem Wert der `TZ` -Umgebungsvariablen werden die folgenden Werte den globalen Variablen `_daylight`, `_timezone`und `_tzname` zugewiesen, wenn `_tzset` aufgerufen wird:  
  
|Globale Variable|Beschreibung|Standardwert|  
|---------------------|-----------------|-------------------|  
|`_daylight`|Wert ungleich 0 (null), wenn eine Sommerzeitzone in der `TZ` -Einstellung angegeben ist; andernfalls 0.|1|  
|`_timezone`|Unterschied in Sekunden zwischen Ortszeit und UTC.|28800 (28800 Sekunden sind gleich 8 Stunden)|  
|`_tzname`[0]|Zeichenfolgenwert des Zeitzonennamens der `TZ` -Umgebungsvariablen; leer, wenn `TZ` nicht festgelegt wurde.|PST|  
|`_tzname`[1]|Zeichenfolgenwert der Sommerzeitzone; leer, wenn die Sommerzeitzone bei der `TZ`-Umgebungsvariablen weggelassen wurde.|PDT|  
  
 Die in der vorangehenden Tabelle aufgeführten Standardwerte für `_daylight` und das `_tzname` -Array entsprechen "PST8PDT." Wenn die DST-Zone in der `TZ` -Umgebungsvariablen weggelassen wird, ist der Wert von `_daylight` 0 und die Funktionen `_ftime`, `gmtime`und `localtime` geben für ihre jeweiligen DST-Flags 0 zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_tzset`|\<time.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
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
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)