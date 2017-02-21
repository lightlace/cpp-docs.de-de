---
title: "Uhr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clock"
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
  - "clock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Berechnen der verwendeten Prozessorzeit"
  - "clock-Funktion"
  - "Berechnen der verwendeten Zeit"
  - "Berechnen der verwendeten Zeit, Berechnen"
  - "Uhrzeit, Prozessor berechnen"
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Uhr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die durch den aufrufenden Prozess verwendete Wanduhrzeit.  
  
## Syntax  
  
```  
clock_t clock( void );  
```  
  
## Rückgabewert  
 Die verstrichene Wanduhrzeit seit dem Start des Prozesses \(verstrichene Zeit in Sekunden mal `CLOCKS_PER_SEC`\).  Wenn die Menge der verstrichenen Zeit nicht verfügbar ist, gibt die Funktion „–1“ zurück, was als ein `clock_t` umgewandelt wird.  
  
## Hinweise  
 Die `clock`\-Funktion informiert darüber, wie viel Wanduhrzeit der aufrufende Prozess verwendet hat.  Beachten Sie, dass diese Angabe nicht zwangsläufig mit ISO C99 konform ist. Diese gibt die CPU\-Zeit als den Rückgabewert an.  Verwenden Sie zum Abrufen der CPU\-Zeit die Win32\-Funktion [GetProcessTimes](http://msdn.microsoft.com/library/windows/desktop/ms683223).  
  
 Ein Zeitgebertick entspricht etwa 1\/`CLOCKS_PER_SEC` Sekunden.  Sofern genügend Zeit gegeben ist, kann der durch `clock` zurückgegebene Wert den maximalen positiven Wert von `clock_t` überschreiten und negativ werden oder den maximalen Absolutwert überschreiten und sich umdrehen.  Verlassen Sie sich in Bezug auf die insgesamt verstrichene Zeit in Prozessen nicht auf diesen Wert, die länger als 214.748 Sekunden oder über 59 Stunden ausgeführt wurden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`clock`|\<time.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_clock.c  
// This example prompts for how long  
// the program is to run and then continuously  
// displays the elapsed time for that period.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
void sleep( clock_t wait );  
  
int main( void )  
{  
   long    i = 6000000L;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   printf( "Time to do %ld empty loops is ", i );  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "%2.1f seconds\n", duration );  
}  
  
// Pauses for a specified number of milliseconds.  
void sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
```  
  
  **Verzögerung für drei Sekunden**  
**Fertig\!  Die Zeit für das Ausführen von 6000000 leeren Schleifen beträgt 0,1 Sekunden**    
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [difftime, \_difftime32, \_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)