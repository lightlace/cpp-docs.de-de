---
title: rand | Microsoft-Dokumentation
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fecd9079de1ae846d83847eb299890d62c29d17
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="rand"></a>rand

Generiert eine pseudozufällige Zahl mithilfe eines Algorithmus bekannten und vollständig reproduziert werden kann. Eine weitere programmgesteuert sichere Version dieser Funktion ist verfügbar. finden Sie unter [Rand_s](../../c-runtime-library/reference/rand-s.md). Zahlen generiert, indem `rand` sind nicht kryptografisch sicher. Verwenden Sie kryptografisch zufallszahlengenerierung ist sicherer, `rand_s` oder die Funktionen deklariert werden, in der C++-Standardbibliothek in [ \<random >](../../standard-library/random.md).

## <a name="syntax"></a>Syntax

```C
int rand( void );
```

## <a name="return-value"></a>Rückgabewert

`rand` gibt eine Pseudozufallszahl zurück, wie oben beschrieben. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die `rand`-Funktion gibt eine pseudozufällige Ganzzahl im Bereich von 0 bis `RAND_MAX` (32767) zurück. Verwenden Sie die [srand](../../c-runtime-library/reference/srand.md)-Funktion, um den Startwert für die Pseudozufallszahl vor dem Aufruf von `rand` zu erstellen.

Die `rand` -Funktion generiert eine bekannte Folge und ist nicht geeignet für die Verwendung als einer kryptografischen Funktion. Verwenden Sie kryptografisch zufallszahlengenerierung ist sicherer, `rand_s` oder die Funktionen deklariert werden, in der C++-Standardbibliothek in [ \<random >](../../standard-library/random.md). Informationen über die Nachteile von `rand()` und die Behebung dieser Schwachpunkte durch `<random>` erhalten Sie in [diesem Video](http://go.microsoft.com/fwlink/?LinkId=397615).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`rand`|\<stdlib.h>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.

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

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)  
[srand](../../c-runtime-library/reference/srand.md)  
[rand_s](../../c-runtime-library/reference/rand-s.md)  