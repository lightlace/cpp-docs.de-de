---
title: clock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clock
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
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3a226377499df1747a022325b762b3cdfdd35ea6
ms.lasthandoff: 02/24/2017

---
# <a name="clock"></a>clock
Berechnet die durch den aufrufenden Prozess verwendete Wanduhrzeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
Die verstrichene Zeit seit der CRT-Initialisierung beim Start des Prozesses, gemessen in `CLOCKS_PER_SEC`-Einheiten pro Sekunde. Wenn die verstrichene Zeit nicht verfügbar ist oder die maximale positive Zeit übersteigt, die als `clock_t`-Typ aufgezeichnet werden kann, gibt die Funktion den Wert `(clock_t)(-1)` zurück.   
  
## <a name="remarks"></a>Hinweise  
Die `clock`-Funktion gibt an, welche Gesamtbetrachtungszeit seit der CRT-Initialisierung beim Start des Prozesses vergangen ist. Beachten Sie, dass diese Funktion nicht streng mit ISO C konform ist, welche die Netto-CPU-Zeit als Rückgabewert nennt. Verwenden Sie zum Abrufen von CPU-Zeiten die Win32-Funktion [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223). Um die verstrichene Zeit in Sekunden zu ermitteln, teilen Sie den Rückgabewert der `clock`-Funktion durch das Makro `CLOCKS_PER_SEC`.  
  
Bei ausreichend Zeit kann der von `clock` zurückgegebene Wert den maximalen positiven Wert von `clock_t` übersteigen. Wenn die Prozessausführung länger gedauert hat, ist der von `clock` zurückgegebene Wert – wie im ISO C99-Standard (7.23.2.1) und im ISO C11-Standard (7.27.2.1) angegeben – stets `(clock_t)(-1)`. Microsoft implementiert `clock_t` als `long`, einen 32-Bit-Integer mit Vorzeichen, und das `CLOCKS_PER_SEC`-Makro ist definiert als 1000. Dies ergibt für die `clock`-Funktion einen maximalen Rückgabewert von 2147483,647 Sekunden oder rund 24,8 Tage. Verlassen Sie sich bei Prozessen, deren Ausführungsdauer länger war, nicht auf den Rückgabewert von `clock`. Sie können die 64-Bit-`time`-Funktion oder die Windows-Funktion [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) verwenden, um verstrichene Prozesszeit für mehrere Jahre zu erfassen.  

## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`clock`|\<time.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_clock.c  
// This sample uses clock() to 'sleep' for three 
// seconds, then determines how long it takes  
// to execute an empty loop 600000000 times.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
// Pauses for a specified number of milliseconds.  
void do_sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
  
const long num_loops = 600000000L;

int main( void )  
{  
   long    i = num_loops;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "Time to do %ld empty loops is ", num_loops );  
   printf( "%2.3f seconds\n", duration );  
}  
```  
  
```Output  
Delay for three seconds  
Done!  
Time to do 600000000 empty loops is 1.354 seconds  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [difftime, _difftime32, _difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
