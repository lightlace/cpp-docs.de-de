---
title: _control87, _controlfp, __control87_2
ms.date: 04/05/2018
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
ms.openlocfilehash: e2ebfdc80a451ebf02563f78a62dd08618f92bcd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340416"
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

Ruft das Gleitkommasteuerwort ab und legt es fest. Eine sicherere Version von **_controlfp** finden Sie unter [_controlfp_s](controlfp-s.md).

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

*new*<br/>
Neue Bitwerte des Steuerworts.

*mask*<br/>
Maske für festzulegende neue Steuerwortbits.

*x86_cw*<br/>
Gefüllt mit dem Steuerwort für die x87-Gleitkommaeinheit. Übergeben Sie 0 (**NULL**) um nur das SSE2-Steuerwort festzulegen.

*sse2_cw*<br/>
Steuerwort für die SSE-Gleitkommaeinheit. Übergeben Sie 0 (**NULL**) nur die X87 festzulegende Word zu steuern.

## <a name="return-value"></a>Rückgabewert

Für **_control87** und **_controlfp**, die Bits im zurückgegebenen Zustand des gleitkommasteuerelements. Eine vollständige Definition der Bits, die von zurückgegeben werden **_control87**, finden Sie unter "float". H.

Für **__control87_2**, der zurückgegebene Wert ist 1, was den Erfolg angibt.

## <a name="remarks"></a>Hinweise

Die **_control87** Funktion ruft ab und legt das gleitkommasteuerwort fest. Mit dem Gleitkommasteuerwort kann das Programm die Genauigkeits-, Rundungs- und Unendlichkeitsmodi im mathematischen Gleitkommapaket je nach Plattform ändern. Sie können auch **_control87** zu maskieren oder Aufheben der Maskierung Gleitkommaausnahmen. Wenn der Wert für *Maske* ist gleich 0 (null) **_control87** Ruft das gleitkommasteuerwort. Wenn *Maske* ist ungleich NULL ist, wird ein neuer Wert für das Steuerwort festgelegt: Für alle, die bit ist (d. h. gleich 1) in *Maske*, das entsprechende Bit in *neue* wird verwendet, um das Steuerwort zu aktualisieren. Das heißt, **Fpcntrl** = ((**Fpcntrl** & ~*Maske*) &#124; (*neue* & *Maske*)) wo **Fpcntrl** das gleitkommasteuerwort ist.

> [!NOTE]
> Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.

**_controlfp** ist eine plattformunabhängige, portable Version der **_control87**. Es ist nahezu identisch mit der **_control87** Funktion auf X86 X64 und ARM-Plattformen. Wenn Sie X86, X64 oder ARM-Plattformen verwenden möchten, verwenden Sie **_control87** oder **_controlfp**.

Der Unterschied zwischen **_control87** und **_controlfp** befindet sich in dem nicht normaler Werte verarbeiten. Für die X86 X64 und ARM-Plattformen **_control87** festlegen und löschen Sie die DENORMAL OPERAND-ausnahmemaske. **_controlfp** ändert nicht die DENORMAL OPERAND-ausnahmemaske. Dieses Beispiel veranschaulicht den Unterschied:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Die möglichen Werte für die maskenkonstante (*Maske*) und die neuen Steuerelementwerte (*neue*) werden in der folgenden Tabelle der Hexadezimalwerten angezeigt. Verwenden Sie die unten aufgeführten portablen Konstanten (**_MCW_EM**, **_EM_INVALID**usw.) als Argumente für diese Funktionen, anstatt die Angabe der Hexadezimalwert Werte explizit.

Intel X86 abgeleitete Plattformen unterstützen die DENORMAL-Eingabe, und geben Werte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Aktivieren die ARM-Plattform und die X64, die Plattformen, die SSE2 unterstützt dass DENORMAL-Operanden und-Ergebnisse gelöscht werden oder auf NULL erzwungen. Die **_controlfp** und **_control87** Funktionen stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

Auf ARM-Plattformen die **_control87** und **_controlfp** Funktionen gelten für das FPSCR-Register. Auf X64 Architekturen, nur das SSE2-Steuerwort, das gespeichert wird, wird im MXCSR-Register betroffen ist. Auf X86 Plattformen **_control87** und **_controlfp** Auswirkung auf die steuerworte sowohl die X87 auch bei SSE2, wenn vorhanden. Die Funktion **__control87_2** ermöglicht sowohl die X87 und SSE2-gleitkommaeinheiten zusammen oder separat gesteuert werden. Wenn beide Einheiten gelten soll, übergeben Sie die Adressen von zwei zu Ganzzahlen **x86_cw** und **sse2_cw**. Wenn Sie nur für eine Einheit gelten soll, übergeben Sie eine Adresse für diesen Parameter aber 0 (**NULL**) für die anderen. Wenn 0 für einen dieser Parameter übergeben wird, hat die Funktion keine Auswirkungen auf diese Gleitkommaeinheit. Diese Funktionalität kann in Situationen nützlich sein, in denen ein Teil des Codes die x87-Gleitkommaeinheit und ein anderer Teil des Codes die SSE2-Gleitkommaeinheit verwendet. Bei Verwendung von **__control87_2** in einem Teil eines Programms verschiedene Werte für die gleitkommasteuerworte festlegen und dann **_control87** oder **_controlfp** genauer Bearbeiten Sie dann das Steuerwort **_control87** und **_controlfp** möglicherweise nicht um den Zustand beider gleitkommaeinheiten darzustellen einzelnes Steuerwort zurückgeben. In diesem Fall legen diese Funktionen die **EM_AMBIGUOUS** Flag im zurückgegebenen ganzzahligen Wert um anzugeben, dass eine Inkonsistenz zwischen den zwei steuerworten besteht. Dies ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleitkommasteuerworte möglicherweise nicht genau dargestellt.

-Architektur wird das Ändern des unendlichkeitsmodus oder die Genauigkeit von Gleitkommawerten werden nicht unterstützt, auf dem ARM und X64. Wenn die genauigkeitssteuermaske auf der X64 dient-Plattform, die Funktion eine Assertion aus und Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** wird nicht unterstützt, auf die ARM oder X64 Architekturen. Bei Verwendung von **__control87_2** und kompilieren Sie das Programm für die ARM oder X64 Architekturen, die der Compiler generiert einen Fehler.

Diese Funktionen werden ignoriert, wenn Sie [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, da die common Language Runtime (CLR) nur die Genauigkeit der standardgleitkommawerte unterstützt.

**Hexadezimalwerte**

Für die **_MCW_EM** das Aufheben-Maske die Ausnahme, was die Hardwareausnahme ermöglicht; das Festlegen der Maske Blendet die Ausnahme. Wenn eine **_EM_UNDERFLOW** oder **_EM_OVERFLOW** wird keine Hardwareausnahme ausgelöst, bis die nächste gleitkommaanweisung ausgeführt wird. Um eine Hardwareausnahme generieren unmittelbar nach **_EM_UNDERFLOW** oder **_EM_OVERFLOW**, rufen Sie die **FWAIT** MASM-Anweisung.

|Format|Farbtonwert|Konstante|Farbtonwert|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (nicht normale Steuerung)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Interrupt-ausnahmemaske)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (unendlichkeitssteuerung)<br /><br /> (Nicht auf ARM oder X64 unterstützt] Plattformen.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (rundungssteuerung)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Precision-Steuerung)<br /><br /> (Nicht unterstützt für ARM oder X64 Plattformen.)|0x00030000|**_PC_24** (24 bits)<br /><br /> **_PC_53** (53 Bits)<br /><br /> **_PC_64** (64 Bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_cntrl87.c
// processor: x86
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87;

    // Show original x87 control word and do calculation.
    control_word_x87 = __control87_2(0, 0,
                                     &control_word_x87, 0);
    printf( "Original: 0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    control_word_x87 = __control87_2(_PC_24, MCW_PC,
                                     &control_word_x87, 0);
    printf( "24-bit:   0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,
                                     &control_word_x87, 0 );
    printf( "Default:  0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0001
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0x0001
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x0001
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
