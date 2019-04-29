---
title: abs, labs, llabs, _abs64
ms.date: 04/05/2018
apiname:
- abs
- _abs64
- labs
- llabs
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
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
ms.openlocfilehash: 61aa0a48757a35708ffb85d2c0525bb4eac82d56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341989"
---
# <a name="abs-labs-llabs-abs64"></a>abs, labs, llabs, _abs64

Berechnet den absoluten Wert des Arguments.

## <a name="syntax"></a>Syntax

```C
int abs( int n );
long labs( long n );
long long llabs( long long n );
__int64 _abs64( __int64 n );
```

```cpp
long abs( long n );   // C++ only
long long abs( long long n );   // C++ only
double abs( double n );   // C++ only
long double abs( long double n );   // C++ only
float abs( float n );   // C++ only
```

### <a name="parameters"></a>Parameter

*n*<br/>
Ein numerischer Wert.

## <a name="return-value"></a>Rückgabewert

Die **abs**, **Labs**, **Llabs** und **_abs64** Funktionen geben den absoluten Wert des Parameters zurück *n*. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **abs** verwenden und zurückgeben **lange**, **lange** **lange**,  **"float"**, **doppelte**, und **lange** **doppelte** Werte. Diese Überladungen sind im Header \<cmath> definiert. In einem C-Programm **abs** immer Double und gibt eine **Int**.

**Microsoft-spezifisch**: Da der mithilfe eines integralen Typs darstellbare Bereich von negativen ganzen Zahlen größer als der entsprechende Bereich von positiven ganzen Zahlen ist, die mithilfe dieses Typs dargestellt werden können, kann für diese Funktionen ein nicht konvertierbares Argument bereitgestellt werden. Wenn der Absolute Wert des Arguments durch den Rückgabetyp dargestellt werden, kann die **abs** Funktionen geben den Argumentwert unverändert zurück. Insbesondere gibt `abs(INT_MIN)` `INT_MIN` zurück, `labs(LONG_MIN)` gibt `LONG_MIN` zurück, `llabs(LLONG_MIN)` gibt `LLONG_MIN` zurück und `_abs64(_I64_MIN)` gibt `_I64_MIN` zurück. Dies bedeutet, dass die **abs** Funktionen können nicht verwendet werden, um einen positiven Wert sicherzustellen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|-----------------------|---------------------------|
|**abs**, **labs**, **llabs**|\<math.h> oder\<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> oder \<math.h|
|**_abs64**|\<stdlib.h>|\<cstdlib> oder \<stdlib.h>|

Verwenden Sie die überladenen Version von **abs** in C++, müssen Sie enthalten die \<Cmath > Header.

## <a name="example"></a>Beispiel

Dieses Programm berechnet die absoluten Werte einiger Zahlen und zeigt sie an.

```C
// crt_abs.c
// Build: cl /W3 /TC crt_abs.c
// This program demonstrates the use of the abs function
// by computing and displaying the absolute values of
// several numbers.

#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <limits.h>

int main( void )
{
    int ix = -4;
    long lx = -41567L;
    long long llx = -9876543210LL;
    __int64 wx = -1;

    // absolute 32 bit integer value
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));

    // absolute long integer value
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));

    // absolute long long integer value
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));

    // absolute 64 bit integer value
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,
        _abs64(wx));

    // Integer error cases:
    printf_s("Microsoft implementation-specific results:\n");
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));
}
```

```Output
The absolute value of -4 is 4
The absolute value of -41567 is 41567
The absolute value of -9876543210 is 9876543210
The absolute value of 0xffffffffffffffff is 0x0000000000000001
Microsoft implementation-specific results:
abs(INT_MIN) returns -2147483648
labs(LONG_MIN) returns -2147483648
llabs(LLONG_MIN) returns -9223372036854775808
_abs64(_I64_MIN) returns 0x8000000000000000
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[imaxabs](imaxabs.md)