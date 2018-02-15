---
title: localtime_s, _localtime32_s, _localtime64_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e30705867a9114fd44b8850d5cf950c2c1d8c4ce
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s
Konvertiert einen Zeitwert und berichtigt die lokale Zeitzone. Dies sind Versionen von [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) mit Sicherheitsverbesserungen wie in den [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `_tm`  
 Ein Zeiger auf die Zeitstruktur, die ausgefüllt wird  
  
 `time`  
 Zeiger auf die gespeicherte Zeit.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`_tm`|`time`|Rückgabewert|Wert in `_tm`|Ruft ungültige Parametertyphandler auf|  
|-----------|------------|------------------|--------------------|---------------------------------------|  
|`NULL`|any|`EINVAL`|Nicht geändert|Ja|  
|Nicht `NULL` (zeigt auf gültigen Speicher)|`NULL`|`EINVAL`|Alle Felder auf-1 festgelegt|Ja|  
|Nicht `NULL` (zeigt auf gültigen Speicher)|kleiner als 0 (null) oder größer als `_MAX__TIME64_T`|`EINVAL`|Alle Felder auf-1 festgelegt|Nein|  
  
 Im Fall der ersten zwei Fehlerbedingungen, wird der ungültige Parameterhandler aufgerufen, so wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_localtime32_s`-Funktion konvertiert eine Zeit, die als ein [time_t](../../c-runtime-library/standard-types.md)-Wert gespeichert ist, und speichert das Ergebnis in einer Struktur vom Typ `tm`. Der `long`-Wert `timer` stellt die Sekunden dar, die seit Mitternacht (00:00:00), 1. Januar 1970, UTC, verstrichen sind. Der Wert wird normalerweise durch einen Aufruf der Funktion `time` abgerufen.  
  
 `_localtime32_s` korrigiert für die lokale Zeitzone, wenn der Benutzer zunächst die globalen Umgebungsvariablen `TZ` festlegt. Wenn `TZ` festgelegt wird, werden drei andere Umgebungsvariablen (`_timezone`, `_daylight`, und `_tzname`) ebenfalls automatisch festgelegt. Wenn die `TZ`-Variable nicht festgelegt ist, versucht `localtime32_s` die Informationen zur Zeitzone zu verwenden, die in der Datum/Uhrzeit-Anwendung in der Systemsteuerung angegeben sind. Wenn diese Information nicht abgerufen werden kann, wird standardmäßig PST8PDT verwendet, was die Zeitzone Pacific (PTC) darstellt. Unter [_tzset](../../c-runtime-library/reference/tzset.md) finden Sie eine Beschreibung dieser Variablen. `TZ` ist eine Microsoft-Erweiterung und nicht Teil der ANSI-Standarddefinition von `localtime`.  
  
> [!NOTE]
>  Die Zielumgebung soll versuchen zu bestimmen, ob die Sommerzeit wirksam ist.  
  
 `_localtime64_s`, das die `__time64_t`-Struktur verwendet, erlaubt das Ausdrücken von Daten über den 18. Januar 3001, 23:59:59 UTC (Koordinierte Weltzeit) hinaus, während `_localtime32_s` Datumsangaben bis zum 18. Januar 2038, 23:59:59, UTC, darstellt.  
  
 `localtime_s` ist eine Inlinefunktion, die `_localtime64_s` auswertet, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32-Bit-`time_t` zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `localtime_s` mit `_localtime32_s` ausgewertet. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.  
  
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
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`localtime_s`|\<time.h>|  
|`_localtime32_s`|\<time.h>|  
|`_localtime64_s`|\<time.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
