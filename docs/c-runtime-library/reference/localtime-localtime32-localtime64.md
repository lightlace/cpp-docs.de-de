---
title: "localtime, _localtime32, _localtime64"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_localtime64"
  - "_localtime32"
  - "localtime"
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
  - "localtime64"
  - "_localtime64"
  - "localtime32"
  - "localtime"
  - "_localtime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "localtime32-Funktion"
  - "_localtime32-Funktion"
  - "_localtime64-Funktion"
  - "localtime64-Funktion"
  - "localtime-Funktion"
  - "Uhrzeit, Konvertieren von Werten"
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# localtime, _localtime32, _localtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Zeitwert ein, und beheben Sie für die lokale Zeitzone. Sicherere Versionen dieser Funktionen sind verfügbar. finden Sie unter [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## Syntax  
  
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
  
#### Parameter  
 `timer`  
 Ein Zeiger auf die gespeicherte Zeit.  
  
## Rückgabewert  
 Ein Zeiger auf das Ergebnis Struktur zurückgegeben oder `NULL` wenn das Datum, an die Funktion übergeben wird:  
  
-   Vor Mitternacht, 1. Januar 1970.  
  
-   Nach 03:14:07 am 19. Januar 2038 UTC \(mit `_time32` und `time32_t`\).  
  
-   Nach 23:59:59, 31. Dezember 3000 UTC \(mit `_time64` und `__time64_t`\).  
  
 `_localtime64`, verwendet der `__time64_t` \-Struktur, die Datumsangaben oben bis 23:59:59, 31. Dezember 3000, koordinierte Weltzeit \(UTC\) ausgedrückt werden können, und `_localtime32` Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellt.  
  
 `localtime` ist eine Inlinefunktion bewertet, um `_localtime64`, und `time_t` entspricht `__time64_t`. Möchten Sie den Compiler, interpretieren erzwingen `time_t`als das alte 32\-Bit `time_t`, können `_USE_32BIT_TIME_T`. Dadurch wird `localtime` ergibt `_localtime32`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt und sie wird auf 64\-Bit\-Plattformen nicht zugelassen.  
  
 Die Felder des Strukturtyps [tm](../../c-runtime-library/standard-types.md) speichern Sie die folgenden Werte an, von denen jeder eine `int`:  
  
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
  
## Hinweise  
 Die `localtime` \-Funktion konvertiert eine Zeit als eine [Time\_t](../../c-runtime-library/standard-types.md) Wert und speichert das Ergebnis in eine Struktur vom Typ `tm`. Die `long` Wert `timer` stellt die Sekunden seit Mitternacht vergangenen \(00: 00:00\), 1. Januar 1970, UTC. Dieser Wert stammt normalerweise aus der `time` Funktion.  
  
 Die 32\-Bit\- und 64\-Bit\-Versionen von `gmtime`, `mktime`, `mkgmtime`, und `localtime` alle verwenden eine einzelne `tm` Struktur für die Konvertierung pro Thread. Jeder Aufruf dieser Routinen zerstört das Ergebnis des vorherigen Aufrufs.  
  
 `localtime` für die lokale Zeitzone korrigiert werden, wenn der Benutzer zunächst die globalen Umgebungsvariablen festgelegt `TZ`. Wenn `TZ` festgelegt wird, werden drei Umgebungsvariablen \(`_timezone`, `_daylight`, und `_tzname`\) werden ebenfalls automatisch festgelegt. Wenn die `TZ` Variable nicht festgelegt ist, `localtime` die Zeitzoneninformationen, die Datum\/Uhrzeit\-Anwendung in der Systemsteuerung verwenden möchte. Wenn diese Informationen nicht abgerufen werden kann, wird PST8PDT, was der Zeitzone Pacific Time bedeutet, wird standardmäßig verwendet. Finden Sie unter [\_tzset](../../c-runtime-library/reference/tzset.md) eine Beschreibung dieser Variablen.`TZ` ist eine Microsoft\-Erweiterung und nicht Teil der ANSI\-Standarddefinition von `localtime`.  
  
> [!NOTE]
>  Die zielumgebung sollten versuchen, um festzustellen, ob die Sommerzeit wirksam ist.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein null\-Zeiger ist oder wenn der Zeitwert negativ ist, rufen diese Funktionen einen Handler für ungültige Parameter an, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`localtime`|\<time.h\>|  
|`_localtime32`|\<time.h\>|  
|`_localtime64`|\<time.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
Dienstag, 12. Februar 10:05:58 Uhr  
```  
  
## .NET Framework-Entsprechung  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)