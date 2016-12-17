---
title: "_ftime, _ftime32, _ftime64"
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
  - "_ftime64"
  - "_ftime"
  - "_ftime32"
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
  - "_ftime32"
  - "_ftime"
  - "_ftime64"
  - "ftime64"
  - "ftime"
  - "ftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime64-Funktion"
  - "_ftime64-Funktion"
  - "Aktuelle Uhrzeit"
  - "_ftime-Funktion"
  - "ftime-Funktion"
  - "_ftime32-Funktion"
  - "ftime32-Funktion"
  - "Uhrzeit, Abrufen aktueller"
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _ftime, _ftime32, _ftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die aktuelle Uhrzeit ab.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md).  
  
## Syntax  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### Parameter  
 `timeptr`  
 Zeiger auf `_timeb`,`__timeb32` oder `__timeb64`\-Struktur.  
  
## Hinweise  
 Die `_ftime`\-Funktion ruft die aktuelle Ortszeit ab und fängt sie in der Struktur, die auf den durch `timeptr` gezeigt wird *.* `_timeb`, `__timeb32` und `__timeb64` werden in Strukturen SYS\\Timeb.h definiert.  Sie enthalten vier Felder, die in der folgenden Tabelle.  
  
 `dstflag`  
 Wert ungleich 0 \(null\), wenn Sommerzeit Momentan aktive für die lokale Zeitzone ist. \(Siehe [\_tzset](../../c-runtime-library/reference/tzset.md) für dazu, wie bestimmt wird Sommerzeit.\)  
  
 `millitm`  
 Sekundenbruchteil in Millisekunden.  
  
 `time`  
 Zeit in Sekunden ab Mitternacht \(00:00: 00\) am 1. Januar 1970 koordinierte Weltzeit \(UTC\).  
  
 `timezone`  
 Unterschied in Minuten, nach Westen Umstieg, zwischen UTC und Ortszeit.  Der Wert `timezone` wird vom Wert der globalen Variable `_timezone` festgelegt \(siehe `_tzset`\).  
  
 `_ftime64`, die die `__timeb64`\-Struktur verwendet, unterstützt von 23:59 die oben angegeben werden können, DateiErstellungsdatumsangaben: 59 3000 am 31. Dezember, UTC; während `_ftime32` nur Datumsangaben von 03:14 darstellt: Am 7. Januar 19 2038, UTC.  Mitternacht am 1. Januar 1970 ist die untere Begrenzung des Zeitraums für alle diese Funktionen.  
  
 `_ftime` entspricht `_ftime64` und `_timeb` enthält eine 64\-Bit\-Zeit.  Dies gilt, es sei denn, `_USE_32BIT_TIME_T` definiert wird, in diesem Fall das alte Verhalten gültig ist; `_ftime` verwendet eine 32\-Bit\-Zeit und `_timeb` enthält eine 32\-Bit\-Zeit.  
  
 `_ftime` überprüft die eigenen Parameter.  Wenn es übergeben wird, ruft ein NULL\-Zeiger als `timeptr`, die den ungültigen Parameterhandler Funktion auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt die Funktion `errno` auf `EINVAL` fest.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_ftime`|\<sys\/types.h und\> sys \<\/timeb.h\>|  
|`_ftime32`|\<sys\/types.h und\> sys \<\/timeb.h\>|  
|`_ftime64`|\<sys\/types.h und\> sys \<\/timeb.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
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
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
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
  
  **Sekunden ab Mitternacht, am 1. Januar 1970 \(UTC\): 1051553334**  
**Millisekunden: 230**  
**Minuten zwischen UTC und Ortszeit: 480**  
**Sommerzeitflag \(1 bedeutet Sommerzeit entsteht wirksam\): 1**  
**Die Uhrzeit lautet Montag am 28. April 11: 08:54.230 2003**   
## .NET Framework-Entsprechung  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)