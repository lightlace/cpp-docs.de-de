---
title: _mm_cvtss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: a3b7ece325d975045046e865e6b090f3f6729558
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263333"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x

**Microsoft-spezifisch**

Generiert die X64 erweiterte Version der konvertieren Skalar einzelne Genauigkeit Gleitkommazahl in 64-Bit-Ganzzahl (`cvtss2si`) Anweisung.

## <a name="syntax"></a>Syntax

```
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

#### <a name="parameters"></a>Parameter

*value*<br/>
[in] Ein `__m128` Struktur, die-Gleitkommawerte enthält.

## <a name="return-value"></a>Rückgabewert

Eine ganze 64-Bit-Zahl ist, das Ergebnis der Konvertierung der ersten Gleitkommawert in eine ganze Zahl.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_cvtss_si64x`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das erste Element der Struktur-Wert wird in eine ganze Zahl konvertiert und ausgegeben. Die Rundung Steuerungsbits im MXCSR werden verwendet, um das Rundungsverhalten zu bestimmen. Der Standardwert, der Rundungsmodus ist round auf die nächste, auf die gerade Zahl gerundet wird, wenn der Dezimalwert 0,5 ist. Da die `__m128` Struktur stellt eine XMM-Register, diese Funktion akzeptiert einen Wert aus dem XMM-Register und schreibt sie in den Systemspeicher.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__m128d](../cpp/m128d.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)