---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
api_name:
- _statusfp2
- _statusfp
- _status87
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
ms.openlocfilehash: 54faf70296ef41f2682f88a8edaa82ee0d2071d4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958093"
---
# <a name="_status87-_statusfp-_statusfp2"></a>_status87, _statusfp, _statusfp2

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

Bei **_status87** und **_statusfp**geben die Bits im zurückgegebenen Wert den Gleit Komma Status an. Siehe float. H-Includedatei für eine Definition der Bits, die von **_statusfp**zurückgegeben werden. Viele Funktionen der mathematischen Bibliothek ändern das Gleitkommastatuswort, was zu unvorhersehbaren Ergebnissen führt. Die Optimierung kann Gleit Komma Vorgänge im Zusammenhang mit Aufrufen von **_status87**, **_statusfp**und verwandten Funktionen neu anordnen, kombinieren und eliminieren. Verwenden Sie die Compileroption [/Od (Deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md) oder die Pragma-Direktive [fenv_access](../../preprocessor/fenv-access.md), um Optimierungen zu verhindern, durch die Gleitkommaoperationen neu angeordnet werden. Rückgabewerte von **_clearfp** und **_statusfp**sowie die Rückgabe Parameter von **_statusfp2**sind zuverlässiger, wenn weniger Gleit Komma Vorgänge zwischen den bekannten Zuständen des Gleit Komma Status Worts ausgeführt werden.

## <a name="remarks"></a>Hinweise

Die **_statusfp** -Funktion Ruft das Gleit Komma Status Wort ab. Das Statuswort ist eine Kombination aus dem Gleitkommaprozessorstatus und anderen Bedingungen, die von dem Handler für Gleitkommaausnahmen – z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf – erkannt werden. Ausnahmen ohne Maskierung werden überprüft, bevor der Inhalt des Statusworts zurückgegeben wird. Dies bedeutet, dass der Aufrufer über ausstehende Ausnahmen informiert wird. Auf x86-Plattformen gibt **_statusfp** eine Kombination aus dem x87-und SSE2-Gleit Komma Status zurück. Auf x64-Plattformen basiert der zurückgegebene Status auf dem MXCSR-Status von SSE. Auf Arm-Plattformen gibt **_statusfp** den Status aus dem fpscr-Register zurück.

**_statusfp** ist eine plattformunabhängige, Portable Version von **_status87**. Es ist identisch mit **_status87** auf Intel (x86)-Plattformen und wird auch von den x64-und Arm-Plattformen unterstützt. Um sicherzustellen, dass Ihr Gleit Komma Code für alle Architekturen portabel ist, verwenden Sie **_statusfp**. Wenn Sie nur x86-Plattformen als Ziel verwenden, können Sie entweder **_status87** oder **_statusfp**verwenden.

Wir empfehlen **_statusfp2** für Chips (z. b. den Pentium IV), die sowohl einen x87-als auch einen SSE2-Gleit Komma Prozessor haben. Für **_statusfp2**werden die Adressen mit dem Gleit Komma Status Wort sowohl für den x87-als auch für den SSE2-Gleit Komma Prozessor gefüllt. Bei einem Chip, der x87-und SSE2-Gleit Komma Prozessoren unterstützt, wird EM_AMBIGUOUS auf 1 festgelegt, wenn **_statusfp** oder **_controlfp** verwendet wird und die Aktion mehrdeutig war, da Sie auf den x87 oder das SSE2-Gleit Komma Status Wort verweisen konnte. Die **_statusfp2** -Funktion wird nur auf x86-Plattformen unterstützt.

Diese Funktionen sind für [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) nicht nützlich, da die Common Language Runtime (CLR) nur die standardmäßige Gleit Komma Genauigkeit unterstützt.

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
