---
title: _control87, _controlfp, __control87_2
ms.date: 08/29/2019
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
ms.openlocfilehash: 75b2870543ec3ddd20d445a492ad4270b91e80d7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218420"
---
# <a name="_control87-_controlfp-__control87_2"></a>_control87, _controlfp, __control87_2

Ruft das Gleitkommasteuerwort ab und legt es fest. Eine sicherere Version von **_controlfp** ist verfügbar. siehe [_controlfp_s](controlfp-s.md).

## <a name="syntax"></a>Syntax

```C
unsigned int _control87(
   unsigned int new,
   unsigned int mask
);
unsigned int _controlfp(
   unsigned int new,
   unsigned int mask
);
int __control87_2(
   unsigned int new,
   unsigned int mask,
   unsigned int* x86_cw,
   unsigned int* sse2_cw
);
```

### <a name="parameters"></a>Parameter

*new*\
Neue Bitwerte des Steuerworts.

*chel*\
Maske für festzulegende neue Steuerwortbits.

*x86_cw*\
Gefüllt mit dem Steuerwort für die x87-Gleitkommaeinheit. Übergeben Sie 0 (**null**), um nur das SSE2-Steuerwort festzulegen.

*sse2_cw*\
Steuerwort für die SSE-Gleitkommaeinheit. Übergeben Sie 0 (**null**), um nur das x87-Steuerwort festzulegen.

## <a name="return-value"></a>Rückgabewert

Bei **_control87** und **_controlfp**geben die Bits im zurückgegebenen Wert den Zustand des Gleit Komma Steuer Elements an. Eine umfassende Definition der Bits, die von **_control87**zurückgegeben werden, finden Sie unter float. Micha.

Für **__control87_2**ist der Rückgabewert 1, was den Erfolg angibt.

## <a name="remarks"></a>Hinweise

Die **_control87** -Funktion Ruft das Gleit Komma Steuerwort ab und legt es fest. Mit dem Gleit Komma Steuerwort kann das Programm die Genauigkeits-, Rundungs-und Unendlichkeits Modi abhängig von der Plattform ändern. Sie können auch **_control87** verwenden, um Gleit Komma Ausnahmen zu maskieren bzw. die Maskierung aufzuheben. Wenn der Wert für *Mask* gleich 0 ist, ruft **_control87** das Gleit Komma Steuerwort ab. Wenn *Mask* ungleich NULL ist, wird ein neuer Wert für das Steuerwort festgelegt: Für jedes Bit, das in *Mask*(d. h. gleich 1) ist, wird das entsprechende Bit in *New* verwendet, um das Steuerwort zu aktualisieren. Anders ausgedrückt: **fpcntrl** = ((**fpcntrl** & ~*Mask*) &#124; (*neue* & *Maske*)), wobei **fpcntrl** das Gleit Komma Steuerwort ist.

> [!NOTE]
> Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.

**_controlfp** ist eine plattformunabhängige, Portable Version von **_control87** , die fast identisch mit der **_control87** -Funktion ist. Wenn Ihr Code mehr als eine Plattform als Ziel hat, verwenden Sie **_controlfp** oder **_controlfp_s**. Der Unterschied zwischen **_control87** und **_controlfp** liegt darin, wie Sie DENORMAL-Werte behandeln. Für x86-, x64-, Arm-und ARM64-Plattformen kann **_control87** die DENORMAL-OPERAND-Ausnahme Maske festlegen und löschen. **_controlfp** ändert nicht die DENORMAL-OPERAND-Ausnahme Maske. Dieses Beispiel veranschaulicht den Unterschied:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Die möglichen Werte für die Masken Konstante (*Maske*) und die neuen Steuerelement Werte (*neu*) werden in der Tabelle Steuerelement Wort Masken und Werte angezeigt. Verwenden Sie die unten aufgeführten portablen Konstanten ( **_MCW_EM**, **_EM_INVALID**usw.) als Argumente für diese Funktionen, anstatt die hexadezimalen Werte explizit anzugeben.

Von Intel x86 abgeleitete Plattformen unterstützen die DENORMAL-Eingabe-und-Ausgabewerte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Die Arm-und ARM64-Plattformen und die x64-Plattformen mit SSE2-Unterstützung ermöglichen es, dass DENORMAL-Operanden und-Ergebnisse geleert oder NULL erzwungen werden. Die **_controlfp** -Funktion und die **_control87** -Funktion stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

Auf Arm-und ARM64-Plattformen gelten die **_control87** -und **_controlfp** -Funktionen für das fpscr-Register. Nur das SSE2-Steuerwort, das im MXCSR-Register gespeichert ist, ist auf x64-Plattformen betroffen. Auf x86-Plattformen beeinflussen **_control87** und **_controlfp** die Steuer Wörter für x87 und SSE2, falls vorhanden.

Mit der **__control87_2** -Funktion können sowohl die Gleit Komma Einheiten x87 als auch SSE2 getrennt oder separat gesteuert werden. Um beide Einheiten zu beeinflussen, übergeben Sie die Adressen von zwei ganzen Zahlen an **x86_cw** und **sse2_cw**. Wenn Sie nur eine Einheit beeinflussen möchten, übergeben Sie eine Adresse für diesen Parameter, übergeben jedoch 0 (**null**) für den anderen. Wenn 0 für einen dieser Parameter übergeben wird, hat die Funktion keine Auswirkungen auf diese Gleitkommaeinheit. Dies ist nützlich, wenn ein Teil des Codes die x87-Gleit Komma Einheit verwendet und ein anderer Teil die SSE2-Gleit Komma Einheit verwendet.

Wenn Sie **__control87_2** verwenden, um unterschiedliche Werte für die Gleit Komma Steuer Wörter festzulegen, kann **_control87** oder **_controlfp** möglicherweise kein einzelnes Steuerwort zurückgeben, um den Zustand beider Gleit Komma Einheiten darzustellen. In einem solchen Fall legen diese Funktionen das **EM_AMBIGUOUS** -Flag im zurückgegebenen ganzzahligen Wert fest, um eine Inkonsistenz zwischen den beiden Steuer Wörtern anzugeben. Das **EM_AMBIGUOUS** -Flag ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleit Komma Steuer Wörter möglicherweise nicht exakt darstellt.

Auf der Arm-, ARM64-und x64-Plattform wird das Ändern des Unendlichkeits Modus oder der Gleit Komma Genauigkeit nicht unterstützt. Wenn die Genauigkeits Steuer Maske auf der x64-Plattform verwendet wird, löst die Funktion eine-Assertion aus, und der Handler für ungültige Parameter wird aufgerufen, wie in [Parameter Validierung](../../c-runtime-library/parameter-validation.md)beschrieben.

> [!NOTE]
> **__control87_2** wird auf der Arm-, ARM64-oder x64-Plattform nicht unterstützt. Wenn Sie **__control87_2** verwenden und Ihr Programm für die arm-, ARM64-oder x64-Plattformen kompilieren, generiert der Compiler einen Fehler.

Diese Funktionen werden ignoriert, wenn Sie für die Kompilierung [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) verwenden. Der Common Language Runtime (CLR) unterstützt nur die standardmäßige Gleit Komma Genauigkeit.

### <a name="control-word-masks-and-values"></a>Steuern von Wort Masken und-Werten

Bei der **_MCW_EM** Mask wird durch das Löschen der Maske die Ausnahme festgelegt, was die Hardware Ausnahme zulässt. das Festlegen der Maske blendet die Ausnahme aus. Wenn **_EM_UNDERFLOW** oder **_EM_OVERFLOW** auftritt, wird keine Hardware Ausnahme ausgelöst, bis die nächste Gleit Komma Anweisung ausgeführt wird. Um eine Hardware Ausnahme direkt nach **_EM_UNDERFLOW** oder **_EM_OVERFLOW**zu generieren, rufen Sie die Anweisung **fwait** MASM auf.

|Format|Farbtonwert|Konstante|Farbtonwert|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (DENORMAL-Steuerelement)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Unterbrechungs Ausnahme Maske)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Unendlich-Steuerelement)<br /><br /> (Wird auf Arm-oder x64-Plattformen nicht unterstützt.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Rundungs Steuerung)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Genauigkeits Steuerung)<br /><br /> (Wird auf Arm-oder x64-Plattformen nicht unterstützt.)|0x00030000|**_PC_24** (24 Bits)<br /><br /> **_PC_53** (53 Bits)<br /><br /> **_PC_64** (64 Bits)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_cntrl87.c
// processor: x86
// compile by using: cl /W4 /arch:IA32 crt_cntrl87.c
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87 = 0;
    int result;

    // Show original x87 control word and do calculation.
    result = __control87_2(0, 0, &control_word_x87, 0 );
    printf( "Original: 0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    result = __control87_2(_PC_24, MCW_PC, &control_word_x87, 0 );
    printf( "24-bit:   0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    result = __control87_2( _CW_DEFAULT, MCW_PC, &control_word_x87, 0 );
    printf( "Default:  0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
24-bit:   0x000a001f
0.1 * 0.1 = 9.999999776482582e-03
Default:  0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
```

## <a name="see-also"></a>Siehe auch

[Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)\
[_clear87, _clearfp](clear87-clearfp.md)\
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)\
[_controlfp_s](controlfp-s.md)
