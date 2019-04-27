---
title: difftime, _difftime32, _difftime64
ms.date: 11/04/2016
apiname:
- _difftime32
- difftime
- _difftime64
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
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
ms.openlocfilehash: 80aaac1696fc82db248b097e73a2d89d81a20346
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288522"
---
# <a name="difftime-difftime32-difftime64"></a>difftime, _difftime32, _difftime64

Ermittelt die Differenz zwischen zwei Uhrzeiten.

## <a name="syntax"></a>Syntax

```C
double difftime( time_t timeEnd, time_t timeStart );
double _difftime32( __time32_t timeEnd, __time32_t timeStart );
double _difftime64( __time64_t timeEnd, __time64_t timeStart );
```

### <a name="parameters"></a>Parameter

*timeEnd*<br/>
Uhrzeit Ende.

*timeStart*<br/>
Uhrzeit Anfang.

## <a name="return-value"></a>Rückgabewert

**Difftime** gibt die verstrichene Zeit in Sekunden an, von *TimeStart* zu *TimeEnd*. Der zurückgegebene Wert ist eine Gleitkommazahl mit doppelter Genauigkeit. Der zurückgegeben Wert ist möglicherweise 0, was auf einen Fehler hindeutet.

## <a name="remarks"></a>Hinweise

Die **Difftime** Funktion berechnet den Unterschied zwischen den beiden angegebenen Zeitwerten *TimeStart* und *TimeEnd*.

Der angegebene Zeitwert muss innerhalb des Bereichs von passen **Time_t**. **Time_t** ist ein 64-Bit-Wert. Das Bereichsende wurde vom 18. Januar 2038, 23:59:59 UTC auf den 31. Dezember 3000, 23:59:59 verlegt. Der untere Bereich von **Time_t** ist nach wie vor Mitternacht, 1. Januar 1970.

**Difftime** ist eine Inlinefunktion, die ausgewertet wird **_difftime32** oder **_difftime64** je nachdem, ob **_USE_32BIT_TIME_T** definiert ist. _difftime32 und _difftime64 können direkt verwendet werden, um die Verwendung einer bestimmten Größe des time-Typs zu erzwingen.

Diese Funktionen überprüfen ihre Parameter. Wenn einer der Parameter Null oder negativ ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen 0 zurück und legen Sie **Errno** zu **EINVAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**difftime**|\<time.h>|
|**_difftime32**|\<time.h>|
|**_difftime64**|\<time.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

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
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038
Multiplying 2 floating point numbers 100 million times...
Program takes      3 seconds.
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
