---
title: difftime, _difftime32, _difftime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f6ab058a86a5635aa341c964644a291f61ba170b
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="difftime-difftime32-difftime64"></a>difftime, _difftime32, _difftime64
Ermittelt die Differenz zwischen zwei Uhrzeiten.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `timer1`  
 Uhrzeit Ende.  
  
 `timer0`  
 Uhrzeit Anfang.  
  
## <a name="return-value"></a>Rückgabewert  
 `difftime` gibt die zwischen `timer0` und `timer1` verstrichene Zeit in Sekunden zurück. Der zurückgegebene Wert ist eine Gleitkommazahl mit doppelter Genauigkeit. Der zurückgegeben Wert ist möglicherweise 0, was auf einen Fehler hindeutet.  
  
## <a name="remarks"></a>Hinweise  
 Die `difftime`-Funktion berechnet die Differenz zwischen den beiden angegebenen Zeitwerten `timer0` und `timer1`.  
  
 Der angegebene Zeitwert muss im Bereich von `time_t` liegen. `time_t` ist ein 64-Bit-Wert. Das Bereichsende wurde vom 18. Januar 2038, 23:59:59 UTC auf den 31. Dezember 3000, 23:59:59 verlegt. Der untere Bereich von `time_t` ist nach wie vor auf den 1. Januar 1970 um Mitternacht festgelegt.  
  
 `difftime` ist eine Inlinefunktion, die als `_difftime32` oder als `_difftime64` ausgewertet wird, je nachdem, ob `_USE_32BIT_TIME_T` definiert wurde. _difftime32 und _difftime64 können direkt verwendet werden, um die Verwendung einer bestimmten Größe des time-Typs zu erzwingen.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn einer der Parameter Null oder negativ ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen 0 zurück und legen `errno` auf `EINVAL` fest.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`difftime`|\<time.h>|  
|`_difftime32`|\<time.h>|  
|`_difftime64`|\<time.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
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
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038Multiplying 2 floating point numbers 100 million times...Program takes      3 seconds.Multiplying 2 floating point numbers 500 million times...  
  
Program takes      5 seconds.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
