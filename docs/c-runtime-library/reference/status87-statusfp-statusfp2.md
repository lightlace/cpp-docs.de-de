---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
ms.openlocfilehash: 271c28dd4e267e5b3b702858cc398689e3e35d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354430"
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

Ruft das Gleitkommastatuswort ab.

## <a name="syntax"></a>Syntax

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>Parameter

*px86*<br/>
Diese Adresse ist mit dem Statuswort für die x87-Gleitkommaeinheit gefüllt.

*pSSE2*<br/>
Diese Adresse ist mit dem Statuswort für die SSE2-Gleitkommaeinheit gefüllt.

## <a name="return-value"></a>Rückgabewert

Für **_status87** und **_statusfp**, die Bits in der zurückgegebene Wert den gleitkommastatus. Finden Sie unter der "float". H-Includedatei für eine Definition der Bits, die von zurückgegeben werden **_statusfp**. Viele Funktionen der mathematischen Bibliothek ändern das Gleitkommastatuswort, was zu unvorhersehbaren Ergebnissen führt. Optimierung neu anordnen, kombinieren und Entfernen von Gleitkommaoperationen um die Aufrufe kann **_status87**, **_statusfp**, und verwandte Funktionen. Verwenden Sie die Compileroption [/Od (Deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md) oder die Pragma-Direktive [fenv_access](../../preprocessor/fenv-access.md), um Optimierungen zu verhindern, durch die Gleitkommaoperationen neu angeordnet werden. Rückgabewerte von **_clearfp** und **_statusfp**, und auch die Rückgabeparameter **_statusfp2**, sind zuverlässiger, wenn weniger Gleitkommaoperationen ausgeführt werden zwischen den bekannten Zuständen des gleitkommastatusworts.

## <a name="remarks"></a>Hinweise

Die **_statusfp** Funktion ruft das gleitkommastatuswort ab. Das Statuswort ist eine Kombination aus dem Gleitkommaprozessorstatus und anderen Bedingungen, die von dem Handler für Gleitkommaausnahmen – z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf – erkannt werden. Ausnahmen ohne Maskierung werden überprüft, bevor der Inhalt des Statusworts zurückgegeben wird. Dies bedeutet, dass der Aufrufer über ausstehende Ausnahmen informiert wird. Auf X86 Plattformen **_statusfp** gibt eine Kombination von der X87 und SSE2-gleitkommastatus zurück. Auf x64-Plattformen basiert der zurückgegebene Status auf dem MXCSR-Status von SSE. Auf ARM-Plattformen **_statusfp** Status aus dem FPSCR-Register zurückgegeben.

**_statusfp** ist eine plattformunabhängige, portable Version der **_status87**. Es ist identisch mit **_status87** auf Intel (x86)-Plattformen und wird auch von der X64 und ARM-Plattformen unterstützt. Um sicherzustellen, dass Ihr gleitkommacode für alle Architekturen portabel ist, verwenden **_statusfp**. Wenn Sie nur X86 Anzielen-Plattformen können Sie mithilfe einer **_status87** oder **_statusfp**.

Es wird empfohlen **_statusfp2** für Chips (wie Pentium IV), die sowohl eine X87 und eine SSE2-Gleitkommaprozessor haben. Für **_statusfp2**, die Adressen mithilfe von für die X87 und SSE2-Gleitkommaprozessor das gleitkommastatuswort ausgefüllt. Bei einem Chip, die X87 und SSE2-Gleitkommaprozessoren unterstützt, wird EM_AMBIGUOUS auf 1 festgelegt **_statusfp** oder **_controlfp** wird verwendet, und die Aktion mehrdeutig war, da er die X87 oder SSE2 verweisen könnte Das gleitkommastatuswort. Die **_statusfp2** Funktion wird nur unterstützt, auf X86 Plattformen.

Diese Funktionen sind nicht nützlich für [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) da die common Language Runtime (CLR) nur die Genauigkeit der standardgleitkommawerte unterstützt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_statusfp.c
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c
// This program creates various floating-point errors and
// then uses _statusfp to display messages that indicate these problems.

#include <stdio.h>
#include <float.h>
#pragma fenv_access(on)

double test( void )
{
   double a = 1e-40;
   float b;
   double c;

   printf("Status = 0x%.8x - clear\n", _statusfp());

   // Assignment into b is inexact & underflows:
   b = (float)(a + 1e-40);
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());

   // c is denormal:
   c = b / 2.0;
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",
            _statusfp());

   // Clear floating point status:
   _clearfp();
   return c;
}

int main(void)
{
   return (int)test();
}
```

```Output
Status = 0x00000000 - clear
Status = 0x00000003 - inexact, underflow
Status = 0x00080003 - inexact, underflow, denormal
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
