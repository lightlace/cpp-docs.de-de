---
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: 69016a4e23b020b2c4c79c6b97a5a76f2b2dc028
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217416"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Microsoft-spezifisch**

Gibt die erweiterte x64-Version der Konvertierung mit einer Gleit Komma Zahl mit einfacher Genauigkeit und einer Gleit Komma Zahl mit einfacher Genauigkeit`cvttss2si`in 64-Bit-Anweisung () aus.

## <a name="syntax"></a>Syntax

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Parameter

*value*\
in Eine `__m128` -Struktur mit Gleit Komma Werten mit einfacher Genauigkeit.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Konvertierung des ersten Gleit Komma Werts in eine 64-Bit-Ganzzahl.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_cvttss_si64x`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die intrinsische unter `_mm_cvtss_si64x` scheidet sich von nur darin, dass ungenaue Konvertierungen in Richtung NULL abgeschnitten werden. Da die `__m128` -Struktur ein XMM-Register darstellt, verschiebt die generierte Anweisung Daten aus einem XMM-Register in den Systemspeicher.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
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

[__m128](../cpp/m128.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
