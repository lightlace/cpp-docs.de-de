---
title: _clear87, _clearfp
ms.date: 04/05/2018
api_name:
- _clearfp
- _clear87
api_location:
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: 4ca49895b881d9e307c1116681bc36f86b167c25
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942953"
---
# <a name="_clear87-_clearfp"></a>_clear87, _clearfp

Ruft das Gleitkommastatuswort ab und löscht dieses.

## <a name="syntax"></a>Syntax

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>Rückgabewert

Die Bits im zurückgegebenen Wert geben den Gleit Komma Status vor dem **_clear87** -oder **_clearfp**-aufrufungspunkt an. Eine umfassende Definition der Bits, die von **_clear87**zurückgegeben werden, finden Sie unter float. h. Viele Funktionen der mathematischen Bibliothek ändern das 8087/80287-Statuswort, was zu unvorhersehbaren Ergebnissen führt. Rückgabewerte von **_clear87** und **_status87** werden zuverlässiger, da weniger Gleit Komma Vorgänge zwischen den bekannten Zuständen des Gleit Komma Status Worts ausgeführt werden.

## <a name="remarks"></a>Hinweise

Die **_clear87** -Funktion löscht die ausnahmeflags im Gleit Komma Status Wort, legt das ausgelastete Bit auf 0 fest und gibt das Status Wort zurück. Das Gleitkommastatuswort ist eine Kombination aus dem 8087/80287-Statuswort und anderen Bedingungen, die von dem Handler für 8087/80287-Ausnahmen erkannt werden, z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf.

**_clearfp** ist eine plattformunabhängige, Portable Version der **_clear87** -Routine. Es ist identisch mit **_clear87** auf Intel (x86)-Plattformen und wird auch von den x64-und Arm-Plattformen unterstützt. Um sicherzustellen, dass Ihr Gleit Komma Code für x64 und Arm portabel ist, verwenden Sie **_clearfp**. Wenn Sie nur x86-Plattformen als Ziel verwenden, können Sie entweder **_clear87** oder **_clearfp**verwenden.

Diese Funktionen sind beim Kompilieren mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) als veraltet markiert, da der Common Language Runtime nur die standardmäßige Gleit Komma Genauigkeit unterstützt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_clear87**|\<float.h>|
|**_clearfp**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
