---
title: _clear87, _clearfp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
dev_langs:
- C++
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 195bd9f78ed9edfa47ec9ebbd2babbee676e5644
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395616"
---
# <a name="clear87-clearfp"></a>_clear87, _clearfp

Ruft das Gleitkommastatuswort ab und löscht dieses.

## <a name="syntax"></a>Syntax

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>Rückgabewert

Die Bits im zurückgegebenen Wert den gleitkommastatus vor dem Aufruf von **_clear87** oder **_clearfp**. Eine vollständige Definition der Bits zurückgegebenes **_clear87**, finden Sie in Float.h. Viele Funktionen der mathematischen Bibliothek ändern das 8087/80287-Statuswort, was zu unvorhersehbaren Ergebnissen führt. Rückgabewerte von **_clear87** und **_status87** sind zuverlässiger, wenn weniger Gleitkommaoperationen zwischen den bekannten Zuständen des gleitkommastatusworts ausgeführt werden.

## <a name="remarks"></a>Hinweise

Die **_clear87** Funktion löscht die ausnahmeflags in das gleitkommastatuswort, legt den busy-Bit auf 0 fest und gibt das statuswort zurück. Das Gleitkommastatuswort ist eine Kombination aus dem 8087/80287-Statuswort und anderen Bedingungen, die von dem Handler für 8087/80287-Ausnahmen erkannt werden, z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf.

**_clearfp** ist eine plattformunabhängige, portable Version von den **_clear87** Routine. Sie ist identisch mit **_clear87** auf Intel (x86)-Plattformen und wird auch von der X64 und ARM-Plattformen unterstützt. Um sicherzustellen, dass Ihr gleitkommacode für X64 und ARM portabel ist, verwenden Sie **_clearfp**. Wenn Ihre nur X86 Zielobjekte Plattformen, verwenden Sie entweder **_clear87** oder **_clearfp**.

Diese Funktionen sind veraltet, beim Kompilieren mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) , da die common Language Runtime nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
