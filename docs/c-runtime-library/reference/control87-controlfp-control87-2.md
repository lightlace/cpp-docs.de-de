---
title: _control87, _controlfp, __control87_2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48d0c3107bf2edc09017ea138e4c8024ce328dd8
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451481"
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

*Maske*<br/>
Maske für festzulegende neue Steuerwortbits.

*x86_cw*<br/>
Gefüllt mit dem Steuerwort für die x87-Gleitkommaeinheit. Übergeben Sie 0 (**NULL**) um nur das SSE2-Steuerwort festzulegen.

*sse2_cw*<br/>
Steuerwort für die SSE-Gleitkommaeinheit. Übergeben Sie 0 (**NULL**) nur die X87 festzulegende Steuerwort.

## <a name="return-value"></a>Rückgabewert

Für **_control87** und **_controlfp**, die Bits des Werts zurückgegebenen geben den Zustand des gleitkommasteuerelements. Eine vollständige Definition der Bits, die von zurückgegeben werden **_control87**, finden Sie unter "float". H.

Für **__control87_2**, der Rückgabewert ist 1, was den Erfolg angibt.

## <a name="remarks"></a>Hinweise

Die **_control87** Funktion ruft ab und legt das gleitkommasteuerwort. Mit dem Gleitkommasteuerwort kann das Programm die Genauigkeits-, Rundungs- und Unendlichkeitsmodi im mathematischen Gleitkommapaket je nach Plattform ändern. Sie können auch **_control87** zu maskieren bzw. Aufheben der Maskierung Gleitkommaausnahmen. Wenn der Wert für *Maske* gleich 0 (null) **_control87** Ruft das gleitkommasteuerwort ab. Wenn *Maske* ist ungleich NULL ist, wird ein neuer Wert für das Steuerwort festgelegt: für jedes Bit, das auf ist (d. h. gleich 1) in *Maske*, das entsprechende Bit in *neue* wird verwendet, um das Steuerelement zu aktualisieren Word. Das heißt, **Fpcntrl** = ((**Fpcntrl** & ~*Maske*) &#124; (*neue* & *Maske*)) wobei **Fpcntrl** das gleitkommasteuerwort ist.

> [!NOTE]
> Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.

**_controlfp** ist eine plattformunabhängige, portable Version von **_control87**. Es ist nahezu identisch mit der **_control87** Funktion auf X86 X64 und ARM-Plattformen. Wenn Sie X86, X64 oder ARM-Plattformen abzielen, verwenden Sie **_control87** oder **_controlfp**.

Der Unterschied zwischen **_control87** und **_controlfp** befindet sich in dem DENORMAL-Werte verarbeiten. Für X86, X64 und ARM-Plattformen **_control87** festlegen und löschen Sie die DENORMAL OPERAND-ausnahmemaske. **_controlfp** ändert nicht die DENORMAL OPERAND-ausnahmemaske. Dieses Beispiel veranschaulicht den Unterschied:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Die möglichen Werte für die maskenkonstante (*Maske*) und die neuen Steuerelementwerte (*neue*) werden in der folgenden Tabelle der Hexadezimalwerten angezeigt. Verwenden Sie die unten aufgeführten portablen Konstanten (**_MCW_EM**, **_EM_INVALID**usw.) als Argumente für diese Funktionen, anstatt die Hexadezimalwerte Angabe Werte explizit.

Intel X86 abgeleitete Plattformen unterstützen die DENORMAL-Eingabe- und-Ausgabewerte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Aktivieren die ARM-Plattform und die X64-Plattformen mit SSE2 unterstützt DENORMAL-Operanden und-Ergebnisse geleert oder dass NULL erzwungen werden. Die **_controlfp** und **_control87** Funktionen stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

Auf ARM-Plattformen die **_control87** und **_controlfp** Funktionen gelten für das FPSCR-Register. Auf X64-Architekturen ist nur das SSE2-Steuerwort, das gespeichert wird, wird im MXCSR-Register betroffen ist. Auf X86 Plattformen **_control87** und **_controlfp** Auswirkungen auf die steuerworte die X87 und die SSE2, falls vorhanden. Die Funktion **__control87_2** ermöglicht die X87 und SSE2-gleitkommaeinheiten zusammen oder getrennt gesteuert werden. Wenn beide Einheiten gelten soll, übergeben Sie die Adressen von zwei ganzen Zahlen um **x86_cw** und **sse2_cw**. Wenn Sie nur für eine Einheit gelten soll, übergeben Sie eine Adresse für diesen Parameter aber 0 (**NULL**) für die anderen. Wenn 0 für einen dieser Parameter übergeben wird, hat die Funktion keine Auswirkungen auf diese Gleitkommaeinheit. Diese Funktionalität kann in Situationen nützlich sein, in denen ein Teil des Codes die x87-Gleitkommaeinheit und ein anderer Teil des Codes die SSE2-Gleitkommaeinheit verwendet. Bei Verwendung von **__control87_2** in einem Teil eines Programms verschiedene Werte für die gleitkommasteuerworte festlegen und dann **_control87** oder **_controlfp** zur weiteren Bearbeiten Sie dann das Steuerwort **_control87** und **_controlfp** möglicherweise in der Lage, um den Zustand beider gleitkommaeinheiten darzustellen einzelnes Steuerwort zurückgeben. In diesem Fall legen diese Funktionen die **EM_AMBIGUOUS** Flag im zurückgegebenen ganzzahligen Wert fest, um anzugeben, dass eine Inkonsistenz zwischen den zwei steuerworten besteht. Dies ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleitkommasteuerworte möglicherweise nicht genau dargestellt.

Auf der ARM- und X64 werden Architekturen, das Ändern des unendlichkeitsmodus oder der Genauigkeit der Gleitkommawerte nicht unterstützt. Bei Verwendung die Genauigkeit Steuerelement Maske auf die X64-Plattform, die Funktion löst eine Assertion aus, und der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** wird nicht unterstützt, auf der ARM- oder eine X64 Architekturen. Bei Verwendung von **__control87_2** und kompilieren Sie das Programm für die ARM- oder eine X64 Architekturen, die der Compiler generiert einen Fehler.

Diese Funktionen werden ignoriert, wenn Sie [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert, da die common Language Runtime (CLR) nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.

**Hexadezimalwerte**

Für die **_MCW_EM** das Aufheben-Maske die Ausnahme, was die Hardwareausnahme ermöglicht; das Festlegen der Maske Blendet die Ausnahme. Wenn eine **_EM_UNDERFLOW** oder **_EM_OVERFLOW** auftritt, wird keine Hardwareausnahme ausgelöst, bis die nächste gleitkommaanweisung ausgeführt wird. Um eine Hardwareausnahme generieren unmittelbar nach **_EM_UNDERFLOW** oder **_EM_OVERFLOW**, rufen Sie die **FWAIT** MASM-Anweisung.

|Format|Farbtonwert|Konstante|Farbtonwert|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (nicht normale Steuerung)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Interrupt-ausnahmemaske)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (unendlichkeitssteuerung)<br /><br /> (Nicht unterstützt auf ARM- oder eine X64] Plattformen.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (rundungssteuerung)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Precision-Steuerung)<br /><br /> (Nicht unterstützte auf ARM- oder eine X64 Plattformen.)|0x00030000|**_PC_24** (24-Bit)<br /><br /> **_PC_53** (53 Bits)<br /><br /> **_PC_64** (64 Bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
