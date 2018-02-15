---
title: localtime, _localtime32, _localtime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fa4d1b9c0f33df5f172500195edd4f50321d4e5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64
Konvertieren Sie einen Zeitwert, und berichtigen Sie die lokale Zeitzone. Sicherere Versionen dieser Funktionen sind verfügbar. Diese finden Sie unter [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `timer`  
 Zeiger auf die gespeicherte Zeit  
  
## <a name="return-value"></a>Rückgabewert  
 Geben Sie einen Zeiger auf das Strukturergebnis oder `NULL` zurück, wenn das Datum, das an die Funktion weitergegeben wurde, wie folgt ist:  
  
-   Vor Mitternacht, 1. Januar 1970  
  
-   Nach 03:14:07 am 19. Januar 2038, UTC (mit `_time32` und `time32_t`)  
  
-   Nach 23:59:59, 31. Dezember 3000 UTC (mit `_time64` und `__time64_t`)  
  
 `_localtime64`, das die `__time64_t`-Struktur verwendet, erlaubt das Ausdrücken von Daten über den 31. Dezember 3000, 23:59:59 UTC (Koordinierte Weltzeit) hinaus, während `_localtime32` Datumsangaben bis zum 18. Januar 2038, 23:59:59, UTC, darstellt.  
  
 `localtime` ist eine Inlinefunktion, die `_localtime64` auswertet, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32-Bit-`time_t` zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `localtime` mit `_localtime32` ausgewertet. Dies ist nicht zu empfehlen, weil die Anwendung nach dem 18. Januar 2038 fehlschlagen kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.  
  
 Die Felder des Strukturtyps [tm](../../c-runtime-library/standard-types.md) speichern die folgenden Werte, von denen jeder `int` darstellt:  
  
 `tm_sec`  
 Sekunden nach Minute (0 - 59).  
  
 `tm_min`  
 Minuten nach Stunde (0 - 59).  
  
 `tm_hour`  
 Stunden nach Mitternacht (0 - 23).  
  
 `tm_mday`  
 Tag des Monats (1-31).  
  
 `tm_mon`  
 Monat (0 - 11; Januar = 0).  
  
 `tm_year`  
 Jahr (aktuelles Jahr minus 1900).  
  
 `tm_wday`  
 Tag der Woche (0 - 6; Sonntag = 0).  
  
 `tm_yday`  
 Tag des Jahres (0 - 365; 1. Januar = 0).  
  
 `tm_isdst`  
 Positiver Wert bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit. Wenn die Umgebungsvariable `TZ` festgelegt ist, setzt die C-Laufzeitbibliothek voraus, dass die Regeln für die USA für die Implementierung der Berechnung der Sommerzeit gelten.  
  
## <a name="remarks"></a>Hinweise  
 Die `localtime`-Funktion konvertiert eine Zeit, die als ein [time_t](../../c-runtime-library/standard-types.md)-Wert gespeichert ist, und speichert das Ergebnis in einer Struktur vom Typ `tm`. Der `long`-Wert `timer` stellt die Sekunden dar, die seit Mitternacht (00:00:00), 1. Januar 1970, UTC, verstrichen sind. Der Wert wird normalerweise durch einen Aufruf der Funktion `time` abgerufen.  
  
 Sowohl die 32-Bit- als auch die 64-Bit-Versionen von `gmtime`, `mktime`, `mkgmtime` und `localtime` nutzen für die Konvertierung pro Thread eine einzige `tm`-Struktur. Jeder Aufruf dieser Routinen zerstört das Ergebnis des vorherigen Aufrufs.  
  
 `localtime` korrigiert für die lokale Zeitzone, wenn der Benutzer zunächst die globalen Umgebungsvariablen `TZ` festlegt. Wenn `TZ` festgelegt wird, werden drei andere Umgebungsvariablen (`_timezone`, `_daylight`, und `_tzname`) ebenfalls automatisch festgelegt. Wenn die `TZ`-Variable nicht festgelegt ist, versucht `localtime` die Informationen zur Zeitzone zu verwenden, die in der Datum/Uhrzeit-Anwendung in der Systemsteuerung angegeben sind. Wenn diese Information nicht abgerufen werden kann, wird standardmäßig PST8PDT verwendet, was die Zeitzone Pacific (PTC) darstellt. Unter [_tzset](../../c-runtime-library/reference/tzset.md) finden Sie eine Beschreibung dieser Variablen. `TZ` ist eine Microsoft-Erweiterung und nicht Teil der ANSI-Standarddefinition von `localtime`.  
  
> [!NOTE]
>  Die Zielumgebung soll versuchen zu bestimmen, ob die Sommerzeit wirksam ist.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein NULL-Zeiger oder der Zeitwert negativ ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`localtime`|\<time.h>|  
|`_localtime32`|\<time.h>|  
|`_localtime64`|\<time.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
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
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)