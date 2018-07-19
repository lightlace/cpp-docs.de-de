---
title: abs, labs, llabs, _abs64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc426bbbc28e6eb3b7e6e4a0fa9fab7e74f62093
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391752"
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

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **abs** verwenden und zurückgeben **lange**, **lange** **lange**,  **"float"**, **doppelte**, und **lange** **doppelte** Werte. Diese Überladungen sind im Header \<cmath> definiert. In einem C-Programm **abs** immer Double und gibt ein "int".

**Microsoft Specific**: Da der Bereich von negativen ganzen Zahlen, die mithilfe eines Ganzzahltyps darstellbare größer als der entsprechende Bereich von positiven ganzen Zahlen, die ist mithilfe dieses Typs dargestellt werden können, ist es möglich ist, geben Sie ein Argument an diese Funktionen, die konvertiert werden können. Wenn der Absolute Wert des Arguments nicht über den Rückgabetyp dargestellt werden kann die **abs** -Funktionen den Argumentwert unverändert zurück. Insbesondere `abs(INT_MIN)` gibt **INT_MIN**, `labs(LONG_MIN)` gibt **LONG_MIN**, `llabs(LLONG_MIN)` gibt **LLONG_MIN**, und `_abs64(_I64_MIN)` Gibt **_I64_MIN**. Dies bedeutet, dass die **abs** Funktionen nicht verwendet werden, um einen positiven Wert sicherzustellen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher C-Header|Erforderlicher C++-Header|
|-------------|-----------------------|---------------------------|
|**Abs**, **Labs**, **Llabs**|\<math.h> oder\<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> oder \<math.h|
|**_abs64**|\<stdlib.h>|\<cstdlib> oder \<stdlib.h>|

Verwenden Sie die überladene Versionen der **abs** in C++, fügen Sie der \<Cmath > Header.

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
[imaxabs](imaxabs.md)<br/>
