---
title: rand
ms.date: 1/02/2018
apiname:
- rand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 67e128fc4adea345807a2d59078a00e3c4bd1f07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440728"
---
# <a name="rand"></a>rand

Generiert eine pseudozufällige Zahl mithilfe eines Algorithmus sehr bekannten und vollständig reproduziert werden kann. Eine weitere programmgesteuert sichere Version dieser Funktion ist verfügbar. finden Sie unter [Rand_s](rand-s.md). Anzahl von generierten **Rand** sind nicht kryptografisch sicher. Verwenden Sie für weitere zufallszahlengenerierung, kryptografisch sichere, [Rand_s](rand-s.md) oder die Funktionen deklariert werden, in der C++-Standardbibliothek in [ \<zufällige >](../../standard-library/random.md).

## <a name="syntax"></a>Syntax

```C
int rand( void );
```

## <a name="return-value"></a>Rückgabewert

**Rand** gibt eine pseudozufällige Zahl ist, wie oben beschrieben. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **Rand** Funktion gibt eine pseudozufällige Ganzzahl im Bereich von 0 bis **RAND_MAX** (32767). Verwenden der [Srand](srand.md) Funktion die Pseudozufallszahl vor dem Aufruf ein Seeding **Rand**.

Die **Rand** -Funktion generiert eine bekannte Folge und ist nicht geeignet für die Verwendung als einer kryptografischen Funktion. Verwenden Sie für weitere zufallszahlengenerierung, kryptografisch sichere, [Rand_s](rand-s.md) oder die Funktionen deklariert werden, in der C++-Standardbibliothek in [ \<zufällige >](../../standard-library/random.md). Informationen, was falsch ist **Rand** und wie \<random > behandelt diese Mängel, finden Sie in diesem Video berechtigt [Rand als schädlich](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**rand**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
