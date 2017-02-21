---
title: "_ftime_s, _ftime32_s, _ftime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftime_s"
  - "_ftime64_s"
  - "_ftime32_s"
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
  - "_ftime_s"
  - "_ftime64_s"
  - "ftime_s"
  - "_ftime32_s"
  - "ftime32_s"
  - "ftime64_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ftime32_s-Funktion"
  - "ftime_s-Funktion"
  - "_ftime64_s-Funktion"
  - "Aktuelle Uhrzeit"
  - "ftime64_s-Funktion"
  - "Uhrzeit, Abrufen aktueller"
  - "_ftime_s-Funktion"
  - "_ftime32_s-Funktion"
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _ftime_s, _ftime32_s, _ftime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die aktuelle Uhrzeit ab. Dies sind die Versionen von [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### Parameter  
 `timeptr`  
 Zeiger auf eine `_timeb,``__timeb32`, oder `__timeb64` Struktur.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler. Wenn `timeptr``NULL` ist, wird `EINVAL` zurückgegeben.  
  
## Hinweise  
 Die `_ftime_s` Funktion ruft die aktuelle lokale Zeit und speichert sie in der Struktur auf den `timeptr`*.* Die `_timeb,``__timeb32`,und`__timeb64` Strukturen in SYS\\Timeb.h definiert sind. Sie enthalten vier Feldern, die in der folgenden Tabelle aufgeführt sind.  
  
 `dstflag`  
 Wert ungleich NULL, wenn die Sommerzeit zurzeit gültig für die lokale Zeitzone ist. \(Siehe [\_tzset](../../c-runtime-library/reference/tzset.md) eine Erläuterung, wie die Sommerzeit festgelegt wird.\)  
  
 `millitm`  
 Sekundenbruchteile in Millisekunden.  
  
 `time`  
 Zeit in Sekunden seit Mitternacht \(00: 00:00\), 1. Januar 1970, koordinierte Weltzeit \(UTC\).  
  
 `timezone`  
 Differenz in Minuten zwischen UTC und lokale westward, verschieben. Der Wert der `timezone` festgelegt ist, aus dem Wert der globalen Variablen `_timezone` \(finden Sie unter `_tzset`\).  
  
 `_ftime64_s`, verwendet der `__timeb64` \-Struktur, Datei\-Erstellung bis 23:59:59, 31. Dezember 3000, UTC; Sie ausgedrückt werden können, und `_ftime32_s` nur Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellt. Mitternacht, ist 1. Januar 1970, die Untergrenze des Zeitraums für alle diese Funktionen.  
  
 `_ftime_s` entspricht dem `_ftime64_s` und `_timeb` enthält eine 64\-Bit\-Uhrzeit. Dies ist der Fall, wenn \_`USE_32BIT_TIME_T` definiert ist, in diesem Fall das alte Verhalten aktiviert ist; \_`ftime_s` verwendet eine 32\-Bit\- und `_timeb` enthält eine 32\-Bit\-Uhrzeit.  
  
 `_ftime_s` überprüft die eigenen Parameter. Wenn einen null\-Zeiger als übergeben `timeptr`, die Funktion wird den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die Ausführung zugelassen wird, setzt die Funktion `errno` auf `EINVAL`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_ftime_s`|\< sys\/types.h \> und \< sys\/timeb.h \>|  
|`_ftime32_s`|\< sys\/types.h \> und \< sys\/timeb.h \>|  
|`_ftime64_s`|\< sys\/types.h \> und \< sys\/timeb.h \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime64_s( &timebuffer );  
  
    time1 = timebuffer.time;  
    millitm1 = timebuffer.millitm;  
    timezone1 = timebuffer.timezone;  
    dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
```Output  
Sekunden seit Mitternacht des 1. Januar 1970 (UTC): 1051553334 Millisekunden: 230 Minuten zwischen UTC und Ortszeit: 480 Sommerzeit Flag (1 bedeutet Sommerzeit gültig ist): 1 die Zeit ist Mo Apr 28 11:08:54.230 2003  
```  
  
## .NET Framework-Entsprechung  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)