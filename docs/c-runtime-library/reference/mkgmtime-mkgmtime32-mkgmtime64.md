---
title: "_mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mkgmtime32"
  - "_mkgmtime64"
  - "_mkgmtime"
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
  - "_mkgmtime64"
  - "mkgmtime32"
  - "_mkgmtime32"
  - "mkgmtime"
  - "mkgmtime64"
  - "_mkgmtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mkgmtime32-Funktion"
  - "time-Funktionen"
  - "mkgmtime-Funktion"
  - "_mkgmtime-Funktion"
  - "Konvertieren von Zeiten"
  - "mkgmtime64-Funktion"
  - "_mkgmtime64-Funktion"
  - "_mkgmtime32-Funktion"
  - "Uhrzeit, Konvertieren"
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _mkgmtime, _mkgmtime32, _mkgmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine UTC\-Zeit, dargestellt durch eine `tm``struct` zu UTC\-Zeit dargestellt, durch eine `time_t` Typ.  
  
## Syntax  
  
```  
  
time_t _mkgmtime(  
   struct tm*   
timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm*   
timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm*   
timeptr  
);  
  
```  
  
#### Parameter  
 `timeptr`  
 Ein Zeiger auf die UTC\-Zeit als einen `struct``tm` zu konvertieren.  
  
## Rückgabewert  
 Eine Menge von Typ `__time32_t` oder `__time64_t` der die Anzahl der Sekunden seit Mitternacht des 1. Januar 1970, in der Coordinated Universal Time \(UTC\) verstrichen. Wenn das Datum außerhalb des zulässigen Bereichs \(siehe Abschnitt "Hinweise"\) oder die Eingabe nicht als gültige Uhrzeit interpretiert werden kann, wird – 1 zurückgegeben.  
  
## Hinweise  
 Die `_mkgmtime32` und `_mkgmtime64` Funktionen konvertieren eine UTC\-Zeit, um eine `__time32_t` oder `__time64_t` Typ, der die Uhrzeit in UTC darstellt. Um eine Ortszeit in UTC\-Zeit zu konvertieren, verwenden Sie `mktime`, `_mktime32`, und `_mktime64` stattdessen.  
  
 `_mkgmtime` ist eine Inlinefunktion, der ergibt `_mkgmtime64`, und `time_t` entspricht `__time64_t`. Möchten Sie den Compiler, interpretieren erzwingen `time_t`als das alte 32\-Bit `time_t`, können `_USE_32BIT_TIME_T`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt \(den maximalen Bereich der 32\-Bit\- `time_t`\), und es darf nicht auf allen auf 64\-Bit\-Plattformen.  
  
 Die Zeit in Struktur übergebenen wird wie folgt auf die gleiche Weise geändert werden, wie sie geändert wurden, mit der `_mktime` Funktionen: die `tm_wday` und `tm_yday` \-Feld festgelegt werden, um neue Werte anhand der Werte der `tm_mday` und `tm_year`. Wenn Sie eine `tm`\-Strukturzeit angeben, legen Sie das Feld `tm_isdst` auf Folgendes fest:  
  
-   Null \(0\) weist darauf hin, dass die Normalzeit gilt.  
  
-   Ein Wert größer als 0 weist darauf hin, dass die Sommerzeit gilt.  
  
-   Ein Wert kleiner als null gibt an, dass der C\-Laufzeitbibliothekscode berechnet, ob Normalzeit oder Sommerzeit gilt.  
  
 Der C\-Laufzeitbibliothek verwendet die TZ\-Umgebungsvariable um den richtigen Sommerzeit zu bestimmen. Wenn TZ nicht festgelegt ist, wird das Betriebssystem abgefragt, um die richtige regionale Sommerzeit Verhalten abzurufen.`tm_isdst` ist ein Pflichtfeld. Wenn nicht festgelegt ist, dessen Wert nicht definiert ist und der Rückgabewert `mktime` ist unvorhersehbar.  
  
 Das Spektrum der `_mkgmtime32` Funktion ist Mitternacht, 1. Januar 1970 UTC bis 23:59:59 am 18. Januar 2038 UTC. Den Bereich der `_mkgmtime64` von Mitternacht, 1. Januar 1970 UTC bis 23:59:59, 31. Dezember 3000, UTC ist. Ein Datum außerhalb des gültigen Bereichs führt ein Rückgabewert von – 1. Den Bereich der `_mkgmtime` davon abhängig, ob `_USE_32BIT_TIME_T` definiert ist. \(Standard\) nicht definiert, der Bereich ist der `_mkgmtime64`ist, andernfalls der Bereich ist beschränkt auf den 32\-Bit\-Adressbereich von `_mkgmtime32`.  
  
 Beachten Sie, dass `gmtime` und `localtime` verwenden einen einzelnen statisch zugewiesenen Puffer für die Konvertierung. Wenn Sie diesen Puffer für angeben `mkgmtime`, der vorherige Inhalt zerstört.  
  
## Beispiel  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## Beispielausgabe  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 Das folgende Beispiel zeigt, wie die Struktur nicht vollständig mit der berechneten Werte der Tag der Woche und Tag des Jahres ausgefüllt ist.  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## Ausgabe  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)