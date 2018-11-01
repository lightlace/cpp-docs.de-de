---
title: _controlfp_s
ms.date: 04/05/2018
apiname:
- _controlfp_s
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
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0624cbfb4870ca87efebac01a8de682b588a4ca3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506677"
---
# <a name="controlfps"></a>_controlfp_s

Ruft das Gleitkommasteuerwort ab und legt es fest. Diese Version von [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md) enthält Sicherheitsverbesserungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parameter

*currentControl*<br/>
Der aktuelle Bitwert des Steuerworts.

*newControl*<br/>
Neue Bitwerte des Steuerworts.

*Maske*<br/>
Maske für festzulegende neue Steuerwortbits.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg NULL, oder ein **Errno** Fehlercode des Wertes.

## <a name="remarks"></a>Hinweise

Die **_controlfp_s** -Funktion ist eine plattformunabhängige und sicherere Version von **_control87**, dem ruft des gleitkommasteuerwort in die Adresse, die in gespeichert ist  *CurrentControl* und legt sie fest, indem *NewControl*. Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an. Mit dem Zustand des Gleitkommasteuerelements kann das Programm die Genauigkeits-, Rundungs- und Unendlichkeitsmodi im mathematischen Gleitkommapaket je nach Plattform ändern. Sie können auch **_controlfp_s** zu maskieren oder Aufheben der Maskierung Gleitkommaausnahmen.

Wenn der Wert für *Maske* ist gleich 0 (null) **_controlfp_s** Ruft das gleitkommasteuerwort ab und speichert den abgerufenen Wert in *CurrentControl*.

Wenn *Maske* ist ungleich NULL ist, wird ein neuer Wert für das Steuerwort festgelegt: für jedes Bit, der festgelegt wird (d. h. gleich 1) in *Maske*, das entsprechende Bit in *neue* wird verwendet, um das Steuerelement aktualisieren Word. Das heißt, *Fpcntrl* = ((*Fpcntrl* & ~*Maske*) &#124; (*NewControl* & *Maske* )), in denen *Fpcntrl* das gleitkommasteuerwort ist. In diesem Szenario *CurrentControl* festgelegt ist, auf den Wert nach Abschluss der Änderung; es ist nicht der alte Steuerwort Bit-Wert.

> [!NOTE]
> Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.

**_controlfp_s** ist nahezu identisch mit der **_control87** (x86) X64 und ARM-Plattformen auf Intel-Funktion. Wenn Sie X86, X64 oder ARM-Plattformen abzielen, können Sie **_control87** oder **_controlfp_s**.

Der Unterschied zwischen **_control87** und **_controlfp_s** ist in dem verarbeiten die denormal-Werte. Für Intel (x86), x 64 und ARM-Plattformen **_control87** festlegen und löschen Sie die DENORMAL OPERAND-ausnahmemaske. **_controlfp_s** ändert nicht die DENORMAL OPERAND-ausnahmemaske. Dieses Beispiel veranschaulicht den Unterschied:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Die möglichen Werte für die maskenkonstante (*Maske*) und die neuen Steuerelementwerte (*NewControl*) werden in der folgenden Tabelle der Hexadezimalwerten angezeigt. Verwenden Sie die unten aufgeführten portablen Konstanten (**_MCW_EM**, **_EM_INVALID**usw.) als Argumente für diese Funktionen, anstatt die Angabe der Hexadezimalwert Werte explizit.

Von Intel (x86) abgeleitete Plattformen unterstützen die DENORMAL-Eingabe- und -Ausgabewerte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Aktivieren die ARM-Plattform und die X64, die Plattformen, die SSE2 unterstützt dass DENORMAL-Operanden und-Ergebnisse gelöscht werden oder auf NULL erzwungen. Die **_controlfp_s**, **_controlfp**, und **_control87** Funktionen stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

Auf ARM-Plattformen die **_controlfp_s** Funktion wendet auf das FPSCR-Register. Auf X64 Architekturen, nur das SSE2-Steuerwort, das gespeichert wird, wird im MXCSR-Register betroffen ist. Auf Intel (x86)-Plattformen **_controlfp_s** wirkt sich auf die steuerworte sowohl die X87 auch bei SSE2, falls vorhanden. Es ist möglich, dass die zwei steuerworte untereinander inkonsistent sind (aufgrund eines vorherigen Aufrufs von [__control87_2](control87-controlfp-control87-2.md), z. B.); Wenn es eine Inkonsistenz zwischen den zwei steuerworten gibt **_controlfp_s** legt die **EM_AMBIGUOUS** flag im *CurrentControl*. Dies ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleitkommasteuerworte möglicherweise nicht genau dargestellt.

-Architektur wird das Ändern des unendlichkeitsmodus oder die Genauigkeit von Gleitkommawerten werden nicht unterstützt, auf dem ARM und X64. Wenn die genauigkeitssteuermaske auf der X64 dient-Plattform, die Funktion eine Assertion aus und Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

Wenn die Maske nicht ordnungsgemäß festgelegt ist, generiert diese Funktion eine Ausnahme wegen eines ungültigen Parameters, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **EINVAL** und **Errno** zu **EINVAL**.

Diese Funktion wird ignoriert, wenn Sie [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, da die common Language Runtime (CLR) nur die Genauigkeit der standardgleitkommawerte unterstützt.

### <a name="mask-constants-and-values"></a>Maskenkonstanten und Werte

Für die **_MCW_EM** deaktivieren-Maske die Ausnahme, was die Hardwareausnahme ermöglicht; das Festlegen der Maske blendet der Ausnahme. Wenn eine **_EM_UNDERFLOW** oder **_EM_OVERFLOW** wird keine Hardwareausnahme ausgelöst, bis die nächste gleitkommaanweisung ausgeführt wird. Generieren Sie eine Hardwareausnahme direkt nach **_EM_UNDERFLOW** oder **_EM_OVERFLOW**, rufen Sie die Anweisung FWAIT MASM.

|Format|Farbtonwert|Konstante|Farbtonwert|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (nicht normale Steuerung)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Interrupt-ausnahmemaske)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (unendlichkeitssteuerung)<br /><br /> (Nicht unterstützt für ARM oder X64 Plattformen.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (rundungssteuerung)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Precision-Steuerung)<br /><br /> (Nicht unterstützt für ARM oder X64 Plattformen.)|0x00030000|**_PC_24** (24 Bits)<br /><br /> **_PC_53** (53 Bits)<br /><br /> **_PC_64** (64 Bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
