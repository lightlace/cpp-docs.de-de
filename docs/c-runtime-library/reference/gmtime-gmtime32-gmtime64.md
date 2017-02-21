---
title: "gmtime, _gmtime32, _gmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gmtime32"
  - "gmtime"
  - "_gmtime64"
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
  - "gmtime"
  - "_gmtime32"
  - "_gmtime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gmtime32-Funktion"
  - "_gmtime64-Funktion"
  - "gmtime-Funktion"
  - "gmtime32-Funktion"
  - "gmtime64-Funktion"
  - "time-Funktionen"
  - "Zeitstrukturkonvertierung"
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# gmtime, _gmtime32, _gmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Zeitwert in eine Struktur. Sicherere Versionen dieser Funktionen sind verfügbar. finden Sie unter [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## Syntax  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### Parameter  
 `timer`  
 Zeiger auf die gespeicherte Zeit. Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht \(00:00: 00\), verstrichen sind. Die Anzeige erfolgt im UTC\-Format.  
  
## Rückgabewert  
 Ein Zeiger auf eine Struktur des Typs [tm](../../c-runtime-library/standard-types.md). Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des `timer`\-Arguments im UTC\-Format. Die Angabe erfolgt nicht in Ortszeit. Jedes dieser Strukturfelder ist wie folgt vom Typ `int`:  
  
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
  
 Sowohl die 32\-Bit\- als auch die 64\-Bit\-Versionen von `gmtime`, `mktime`, `mkgmtime` und `localtime` nutzen für die Konvertierung pro Thread eine gemeinsame `tm`\-Struktur. Jeder Aufruf dieser Funktionen zerstört das Ergebnis des vorherigen Aufrufs. Wenn `timer` ein Datum vor Mitternacht \(1. Januar 1970\) darstellt, gibt `gmtime``NULL` zurück. Es gibt keine Fehlerrückgabe.  
  
 `_gmtime64`, verwendet der `__time64_t` \-Struktur, die Datumsangaben oben bis 23:59:59, 31. Dezember 3000 UTC ausgedrückt werden können, während `_gmtime32` nur Datumsangaben bis 23:59:59 am 18. Januar 2038 UTC darstellen. Der 1. Januar 1970 \(Mitternacht\) ist der untere Datumsbereich für beide Funktionen.  
  
 `gmtime` ist eine Inlinefunktion, die `_gmtime64` auswertet, und `time_t` entspricht `__time64_t`, sofern nicht, `_USE_32BIT_TIME_T` definiert ist. Wenn Sie den Compiler zwingen müssen, `time_t` das alte 32\-Bit\-`time_t` zu interpretieren, können Sie `_USE_32BIT_TIME_T` definieren. Dies führt jedoch dazu, dass `gmtime` in `_gmtime32` eingebunden wird und dass `time_t` als `__time32_t` definiert wird. Diese Aktion sollte nicht durchgeführt werden, da sie auf 64\-Bit\-Plattformen nicht zugelassen ist und die Anwendung auf jedem Fall nach dem 18. Januar 2038 fehlschlägt.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein null\-Zeiger ist oder wenn der Zeitwert negativ ist, rufen diese Funktionen einen Handler für ungültige Parameter an, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
## Hinweise  
 Die `_gmtime32`\-Funktion gliedert den `timer`\-Wert und speichert diesen in eine statistisch zugeordnete Struktur vom Typ `tm`, die in TIME.H. definiert ist. Der Wert von `timer` wird in der Regel durch einen Aufruf der `time`\-Funktion abgerufen.  
  
> [!NOTE]
>  In den meisten Fällen versucht die Zielumgebung zu bestimmen, ob die Sommerzeit wirksam ist. Die C\-Laufzeitbibliothek geht davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit \(DST, Daylight Saving Time\) angewendet werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`gmtime`|\<time.h\>|  
|`_gmtime32`|\<time.h\>|  
|`_gmtime64`|\<time.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
  
      // crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Die koordinierte Weltzeit ist Dienstag, 12. Februar 2002, 23:11:31.  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)