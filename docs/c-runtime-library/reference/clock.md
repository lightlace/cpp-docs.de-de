---
title: clock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: d7deb43509e9d5b74d43006b81326a3fa0cbf09b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="clock"></a>clock

Berechnet die durch den aufrufenden Prozess verwendete Wanduhrzeit.

## <a name="syntax"></a>Syntax

```C
clock_t clock( void );
```

## <a name="return-value"></a>Rückgabewert

Die verstrichene Zeit seit die CRT-Initialisierung beim Start des Prozesses, gemessen in **CLOCKS_PER_SEC** Einheiten pro Sekunde. Wenn die verstrichene Zeit nicht verfügbar ist oder überschreitet die maximale positive Zeit, die als aufgezeichnet werden, kann eine **clock_t erweitert** Typ, der die Funktion gibt den Wert `(clock_t)(-1)`.

## <a name="remarks"></a>Hinweise

Die **Uhr** -Funktion informiert darüber, wie viel wanduhrzeit seit die CRT-Initialisierung beim Start des Prozesses überschritten hat. Beachten Sie, dass diese Funktion nicht streng mit ISO C konform ist, welche die Netto-CPU-Zeit als Rückgabewert nennt. Verwenden Sie zum Abrufen von CPU-Zeiten die Win32-Funktion [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223). Um die verstrichene Zeit in Sekunden zu ermitteln, teilen Sie den Rückgabewert von der **Uhr** Funktion durch das Makro **CLOCKS_PER_SEC**.

Sofern genügend Zeit gegeben, der zurückgegebene Wert von **Uhr** können überschreiten der maximalen positiven Wert von **clock_t erweitert**. Wenn der Prozess hat mehr ausgeführt werden, den Rückgabewert von **Uhr** ist immer `(clock_t)(-1)`, gemäß dem Standard ISO C99 (7.23.2.1) und ISO C11-Standards (7.27.2.1). Microsoft implementiert **clock_t erweitert** als eine **lange**, eine 32-Bit-Ganzzahl mit Vorzeichen, und die **CLOCKS_PER_SEC** -Makro wird definiert als 1000. Dadurch werden maximal **Uhr** Funktion Rückgabewert 2147483,647 Sekunden oder ungefähr 24.8 Tage. Verlassen Sie sich nicht auf den Rückgabewert von **Uhr** in Prozessen, die länger als dieser Zeitraum ausgeführt haben. Können Sie die 64-Bit- [Zeit](time-time32-time64.md) Funktion oder die Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) Funktion Datensatz Prozesses verstrichene Zeiten von vielen Jahren.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**clock**|\<time.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[difftime, _difftime32, _difftime64](difftime-difftime32-difftime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
