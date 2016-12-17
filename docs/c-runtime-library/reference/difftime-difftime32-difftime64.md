---
title: "difftime, _difftime32, _difftime64"
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
  - "_difftime32"
  - "difftime"
  - "_difftime64"
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
  - "_difftime64"
  - "difftime"
  - "difftime64"
  - "_difftime32"
  - "difftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_difftime32-Funktion"
  - "difftime-Funktion"
  - "Zeit, Suchen des Unterschieds"
  - "difftime64-Funktion"
  - "_difftime64-Funktion"
  - "difftime32-Funktion"
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# difftime, _difftime32, _difftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht den Unterschied zwischen zwei Mal.  
  
## Syntax  
  
```  
double difftime(   
   time_t timer1,  
   time_t timer0   
);  
double _difftime32(   
   __time32_t timer1,  
   __time32_t timer0   
);  
double _difftime64(   
   __time64_t timer1,  
   __time64_t timer0   
);  
```  
  
#### Parameter  
 `timer1`  
 Endzeit.  
  
 `timer0`  
 Startzeit.  
  
## Rückgabewert  
 `difftime` Gibt die verstrichene Zeit in Sekunden an, von `timer0` zu `timer1`. Der zurückgegebene Wert ist eine Gleitkommazahl mit doppelter Genauigkeit. Der zurückgegebene Wert möglicherweise 0, gibt einen Fehler.  
  
## Hinweise  
 Die `difftime` \-Funktion berechnet den Unterschied zwischen den zwei angegebenen Zeitwerten `timer0` und `timer1`.  
  
 Der angegebene Zeitwert muss innerhalb des Bereichs von passen `time_t`.`time_t` ist ein 64\-Bit\-Wert. Daher wurde das Ende des Bereichs von 23:59:59 18. Januar 2038, UTC bis 23:59:59, 31. Dezember 3000 erweitert. Den unteren Bereich der `time_t` ist nach wie vor Mitternacht, 1. Januar 1970.  
  
 `difftime` ist eine Inlinefunktion, die entweder ergibt `_difftime32` oder `_difftime64` je nachdem, ob `_USE_32BIT_TIME_T` definiert ist. \_difftime32 und \_difftime64 können verwendet werden, direkt auf die Verwendung einer bestimmten Größe vom Time\-Typ zu erzwingen.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn der Parameter ist NULL oder negativ ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen 0 zurück und legen Sie `errno` auf `EINVAL`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`difftime`|\<time.h\>|  
|`_difftime32`|\<time.h\>|  
|`_difftime64`|\<time.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```cpp  
// crt_difftime.c  
// This program calculates the amount of time  
// needed to do a floating-point multiply 100 million times.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
#include <float.h>  
  
double RangedRand( float range_min, float range_max)  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min);  
}  
  
int main( void )  
{  
   time_t   start, finish;  
   long     loop;  
   double   result, elapsed_time;  
   double   arNums[3];  
  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   arNums[0] = RangedRand(1, FLT_MAX);  
   arNums[1] = RangedRand(1, FLT_MAX);  
   arNums[2] = RangedRand(1, FLT_MAX);  
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );  
  
   printf( "Multiplying 2 numbers 100 million times...\n" );  
  
   time( &start );  
   for( loop = 0; loop < 100000000; loop++ )  
      result = arNums[loop%3] * arNums[(loop+1)%3];   
   time( &finish );  
  
   elapsed_time = difftime( finish, start );  
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );  
}  
  
```  
  
```Output  
Mit zufälligen Zahlen 1.04749e + 038 2.01482e + 038 1.72737e 038Multiplying 2 auf die Zahlen 100 Millionen Mal... 3 Sekunden übernommen. Multiplikation Gleitkomma-2 zeigen die Zahlen 500 Millionen Mal... 5 Sekunden übernommen.  
```  
  
## .NET Framework-Entsprechung  
 [System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)