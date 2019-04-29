---
title: _mm_cvttss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: cfdea6ded622cbcbe42bd555edb3029fabad7823
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396651"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x

**Microsoft-spezifisch**

Gibt die X64 erweiterte Version von Convert mit Abschneiden Floating-Point-Wert in 64-Bit-Ganzzahl mit einfacher Genauigkeit (`cvttss2si`) Anweisung.

## <a name="syntax"></a>Syntax

```
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

#### <a name="parameters"></a>Parameter

*value*<br/>
[in] Ein `__m128` Struktur, die Gleitkommawerte mit einfacher Genauigkeit enthält.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Konvertierung von der ersten Gleitkommawert in eine 64-Bit-Ganzzahl.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_cvttss_si64x`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die systeminterne Funktion unterscheidet sich von `_mm_cvtss_si64x` nur darin, dass ungenaue Konvertierungen in Richtung Null abgeschnitten werden. Da die `__m128` -Struktur stellt ein XMM-Register dar, die generierte Anweisung verschiebt Daten aus einem XMM-Register im Systemspeicher.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__m128](../cpp/m128.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)