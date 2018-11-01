---
title: hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
ms.date: 04/05/2018
apiname:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
ms.openlocfilehash: ea25ea87a0ec23a0e98dbdc7bb92ce691fc2fa0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439532"
---
# <a name="hypot-hypotf-hypotl-hypot-hypotf-hypotl"></a>hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl

Berechnet die Hypotenuse.

## <a name="syntax"></a>Syntax

```C
double hypot(
   double x,
   double y
);
float hypotf(
   float x,
   float y
);
long double hypotl(
   long double x,
   long double y
);
double _hypot(
   double x,
   double y
);
float _hypotf(
   float x,
   float y
);
long double _hypotl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parameter

*X*, *y*<br/>
Gleitkommawerte.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Hypot** gibt die Länge der Hypotenuse; bei Überlauf **Hypot** gibt INF (Unendlichkeit) zurück, und die **Errno** auf festgelegt ist **ERANGE** . Sie können **_matherr** Fehlerbehandlung zu ändern.

Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Hypot** -Funktionen berechnen die Länge der Hypotenuse eines rechtwinkligen Dreiecks, wird die Länge der beiden Seiten *x* und *y* (das heißt, die Quadratwurzel von *x*<sup>2</sup> + *y*<sup>2</sup>).

Die Versionen der Funktionen mit führenden Unterstrichen unterstützen die Kompatibilität mit früheren Standards. Ihr Verhalten ist mit den Versionen identisch, die keine führende Unterstriche haben. Es empfiehlt sich, die Versionen ohne führende Unterstriche für neuen Code zu verwenden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**Hypot**, **Hypotf**, **Hypotl**, **_hypot**, **_hypotf**, **_hypotl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_hypot.c
// This program prints the hypotenuse of a right triangle.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 3.0, y = 4.0;

   printf( "If a right triangle has sides %2.1f and %2.1f, "
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );
}
```

```Output
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[_matherr](matherr.md)<br/>