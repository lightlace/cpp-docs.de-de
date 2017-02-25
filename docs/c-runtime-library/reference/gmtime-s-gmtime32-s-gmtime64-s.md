---
title: "gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gmtime32_s"
  - "gmtime_s"
  - "_gmtime64_s"
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
  - "_gmtime_s"
  - "gmtime64_s"
  - "gmtime32_s"
  - "_gmtime64_s"
  - "gmtime_s"
  - "_gmtime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gmtime_s-Funktion"
  - "gmtime32_s-Funktion"
  - "time-Funktionen"
  - "gmtime64_s-Funktion"
  - "_gmtime64_s-Funktion"
  - "Zeitstrukturkonvertierung"
  - "_gmtime_s-Funktion"
  - "_gmtime32_s-Funktion"
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# gmtime_s, _gmtime32_s, _gmtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Zeitwert in eine Struktur. Dies sind die Versionen der [\_gmtime32 \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### Parameter  
 `_tm`  
 Zeiger auf eine `tm` Struktur. Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des `timer`\-Arguments im UTC\-Format. Die Angabe erfolgt nicht in Ortszeit.  
  
 `time`  
 Ein Zeiger auf die gespeicherte Zeit. Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht \(00:00: 00\), verstrichen sind. Die Anzeige erfolgt im UTC\-Format.  
  
## Rückgabewert  
 NULL, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. eine Liste dieser Fehler finden Sie unter [Errno](../../c-runtime-library/errno-constants.md).  
  
### Fehlerbedingungen  
  
|`_tm`|`time`|Zurück|Wert in `_tm`|  
|-----------|------------|------------|-------------------|  
|`NULL`|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` \(verweist auf gültige Speicher\)|`NULL`|`EINVAL`|Alle Felder auf\-1 festgelegt.|  
|Nicht `NULL`|\< 0|`EINVAL`|Alle Felder auf\-1 festgelegt.|  
  
 Bei den ersten beiden Fehlerzustände Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## Hinweise  
 Die `_gmtime32_s` \-Funktion gliedert den `time` \-Wert und speichert diesen in eine Struktur vom Typ `tm`, die in Time.h definiert. Die Adresse dieser Struktur übergeben `_tm`. Der Wert der `time` abgerufen, in der Regel von einem Aufruf der `time` Funktion.  
  
> [!NOTE]
>  Die zielumgebung sollten versuchen, um festzustellen, ob die Sommerzeit wirksam ist. Die C\-Laufzeitbibliothek geht davon aus den Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit.  
  
 Jedes dieser Strukturfelder ist vom Typ `int`, wie in der folgenden Tabelle dargestellt.  
  
 `tm_sec`  
 Sekunden nach Minute \(0 \- 59\).  
  
 `tm_min`  
 Minuten nach Stunde \(0 \- 59\).  
  
 `tm_hour`  
 Stunden seit Mitternacht \(0 \- 23\).  
  
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
 Für `gmtime` immer 0.  
  
 `_gmtime64_s`, verwendet der `__time64_t` \-Struktur, die Datumsangaben oben bis 23:59:59, 31. Dezember 3000, UTC; ausgedrückt werden können, und `gmtime32_s` nur Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellen. Mitternacht, ist 1. Januar 1970, die untere Grenze für den Datumsbereich für beide dieser Funktionen.  
  
 `gmtime_s` ist eine Inlinefunktion bewertet, um `_gmtime64_s` und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32\-Bit\-`time_t` zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `gmtime_s` eingebunden werden `_gmtime32_s`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt und sie wird auf 64\-Bit\-Plattformen nicht zugelassen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`gmtime_s`|\<time.h\>|  
|`_gmtime32_s`|\<time.h\>|  
|`_gmtime64_s`|\<time.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Koordinierte Weltzeit ist fr Apr 25 20:12:33 2003  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)