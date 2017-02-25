---
title: "localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_localtime64_s"
  - "_localtime32_s"
  - "localtime_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_localtime32_s"
  - "localtime32_s"
  - "localtime_s"
  - "localtime64_s"
  - "_localtime64_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_localtime64_s-Funktion"
  - "localtime32_s-Funktion"
  - "_localtime32_s-Funktion"
  - "localtime64_s-Funktion"
  - "Uhrzeit, Konvertieren von Werten"
  - "localtime_s-Funktion"
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# localtime_s, _localtime32_s, _localtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Zeitwert ein, und für die lokale Zeitzone korrigiert. Dies sind die Versionen von [Localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
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
  
#### Parameter  
 `_tm`  
 Ein Zeiger auf die Zeitstruktur ausgefüllt werden.  
  
 `time`  
 Zeiger auf die gespeicherte Zeit.  
  
## Rückgabewert  
 NULL, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [Errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Fehlerbedingungen  
  
|`_tm`|`time`|Rückgabewert|Wert in `_tm`|Handler für ungültige Parameter aufgerufen|  
|-----------|------------|------------------|-------------------|------------------------------------------------|  
|`NULL`|any|`EINVAL`|Nicht geändert|Ja|  
|Nicht `NULL` \(verweist auf gültige Speicher\)|`NULL`|`EINVAL`|Alle Felder festgelegt auf\-1.|Ja|  
|Nicht `NULL` \(verweist auf gültige Speicher\)|kleiner als 0 oder größer als `_MAX__TIME64_T`|`EINVAL`|Alle Felder festgelegt auf\-1.|Nein|  
  
 Bei den ersten beiden Fehlerzustände Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## Hinweise  
 Die `_localtime32_s` \-Funktion konvertiert eine Zeit als eine [Time\_t](../../c-runtime-library/standard-types.md) Wert und speichert das Ergebnis in eine Struktur vom Typ `tm`. Die `long` Wert `timer` stellt die Sekunden seit Mitternacht vergangenen \(00: 00:00\), 1. Januar 1970, UTC. Dieser Wert stammt normalerweise aus der `time` Funktion.  
  
 `_localtime32_s` für die lokale Zeitzone korrigiert werden, wenn der Benutzer zunächst die globalen Umgebungsvariablen festgelegt `TZ`. Wenn `TZ` festgelegt wird, werden drei Umgebungsvariablen \(`_timezone`, `_daylight`, und `_tzname`\) werden ebenfalls automatisch festgelegt. Wenn die `TZ` Variable nicht festgelegt ist, `localtime32_s` versucht, die Informationen zur Zeitzone angegeben, in der Datum\/Uhrzeit\-Anwendung in der Systemsteuerung verwenden. Wenn diese Informationen nicht abgerufen werden kann, wird PST8PDT, was die Zeitzone Pacific Time bedeutet, wird standardmäßig verwendet. Finden Sie unter [\_tzset](../../c-runtime-library/reference/tzset.md) eine Beschreibung dieser Variablen.`TZ` ist eine Microsoft\-Erweiterung und nicht Teil der ANSI\-Standarddefinition von `localtime`.  
  
> [!NOTE]
>  Die zielumgebung sollten versuchen, um festzustellen, ob die Sommerzeit wirksam ist.  
  
 `_localtime64_s`, verwendet der `__time64_t` \-Struktur, die Datumsangaben oben bis 23:59:59, 31. Dezember 3000, koordinierte Weltzeit \(UTC\) ausgedrückt werden können, und `_localtime32_s` Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellt.  
  
 `localtime_s` ist eine Inlinefunktion bewertet, um `_localtime64_s`, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32\-Bit\-`time_t` zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `localtime_s` ergibt `_localtime32_s`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt und sie wird auf 64\-Bit\-Plattformen nicht zugelassen.  
  
 Die Felder des Strukturtyps [tm](../../c-runtime-library/standard-types.md) speichern Sie die folgenden Werte an, von denen jeder eine `int`.  
  
 `tm_sec`  
 Sekunden nach Minute \(0 \- 59\).  
  
 `tm_min`  
 Minuten nach Stunde \(0 \- 59\).  
  
 `tm_hour`  
 Stunden nach Mitternacht \(0\-23\).  
  
 `tm_mday`  
 Tag im Monat \(1 \- 31\).  
  
 `tm_mon`  
 Monat \(0 \- 11; Januar \= 0\).  
  
 `tm_year`  
 Jahr \(aktuelles Jahr minus 1900\).  
  
 `tm_wday`  
 Tag der Woche \(0 \- 6; Sonntag \= 0\).  
  
 `tm_yday`  
 Tag des Jahres \(0 \- 365; Januar 1 \= 0\).  
  
 `tm_isdst`  
 Positive Wert, wenn die Sommerzeit gültig ist; 0, wenn die Sommerzeit nicht aktiviert ist; negativer Wert, wenn der Status der Sommerzeit unbekannt ist. Wenn die `TZ` \-Umgebungsvariable festgelegt ist, wird der C\-Laufzeitbibliothek geht davon aus Regeln, die den Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit \(DST\).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`localtime_s`|\<time.h\>|  
|`_localtime32_s`|\<time.h\>|  
|`_localtime64_s`|\<time.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
  
## Beispielausgabe  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## .NET Framework-Entsprechung  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)