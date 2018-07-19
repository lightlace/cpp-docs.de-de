---
title: _status87, _statusfp, _statusfp2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69297d7ff1e3ec40cfe4fc22dec86c356d1697d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412555"
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

Für **_status87** und **_statusfp**, die Bits in der zurückgegebene Wert den gleitkommastatus. Finden Sie in der "float". H-Includedatei für eine Definition der Bits, die von zurückgegeben werden **_statusfp**. Viele Funktionen der mathematischen Bibliothek ändern das Gleitkommastatuswort, was zu unvorhersehbaren Ergebnissen führt. Optimierung neu anordnen, kombinieren und Entfernen von Gleitkommaoperationen um die Aufrufe kann **_status87**, **_statusfp**, und verwandte Funktionen verweisen. Verwenden Sie die Compileroption [/Od (Deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md) oder die Pragma-Direktive [fenv_access](../../preprocessor/fenv-access.md), um Optimierungen zu verhindern, durch die Gleitkommaoperationen neu angeordnet werden. Rückgabewerte von **_clearfp** und **_statusfp**, und auch die Rückgabeparameter von **_statusfp2**, sind zuverlässiger, wenn weniger Gleitkommaoperationen ausgeführt werden zwischen den bekannten Zuständen des gleitkommastatusworts.

## <a name="remarks"></a>Hinweise

Die **_statusfp** Funktion ruft das gleitkommastatuswort ab. Das Statuswort ist eine Kombination aus dem Gleitkommaprozessorstatus und anderen Bedingungen, die von dem Handler für Gleitkommaausnahmen – z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf – erkannt werden. Ausnahmen ohne Maskierung werden überprüft, bevor der Inhalt des Statusworts zurückgegeben wird. Dies bedeutet, dass der Aufrufer über ausstehende Ausnahmen informiert wird. Auf X86 Plattformen **_statusfp** gibt eine Kombination der X87 und SSE2-gleitkommastatus zurück. Auf x64-Plattformen basiert der zurückgegebene Status auf dem MXCSR-Status von SSE. Auf ARM-Plattformen **_statusfp** Status aus dem FPSCR-Register zurückgegeben.

**_statusfp** ist eine plattformunabhängige, portable Version von **_status87**. Sie ist identisch mit **_status87** auf Intel (x86)-Plattformen und wird auch von der X64 und ARM-Plattformen unterstützt. Um sicherzustellen, dass Ihr gleitkommacode für alle Architekturen portabel ist, verwenden Sie **_statusfp**. Wenn Ihre nur X86 Zielobjekte Plattformen, verwenden Sie entweder **_status87** oder **_statusfp**.

Wir empfehlen **_statusfp2** für Chips (wie Pentium IV), die eine X87 und SSE2-Gleitkommaprozessor haben. Für **_statusfp2**, die Adressen ausgefüllt, indem das gleitkommastatuswort für die X87 oder SSE2-Gleitkommaprozessor. Bei einem Chip, der X87 und SSE2-Gleitkommaprozessoren unterstützt, wird EM_AMBIGUOUS auf 1 festgelegt **_statusfp** oder **_controlfp** wird verwendet, und die Aktion war mehrdeutig, da er auf die X87 oder SSE2 verweisen könnte Das gleitkommastatuswort. Die **_statusfp2** Funktion wird nur unterstützt, auf X86 Plattformen.

Diese Funktionen sind nicht sinnvoll für [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) , da die common Language Runtime (CLR) nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
