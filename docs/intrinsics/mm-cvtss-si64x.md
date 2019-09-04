---
title: _mm_cvtss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: 6079ed7846a35ff16355f0341d63430f9846057f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217433"
---
# <a name="_mm_cvtss_si64x"></a>_mm_cvtss_si64x

**Microsoft-spezifisch**

Generiert die erweiterte x64-Version der Gleit Komma Zahl mit einer Gleit Komma Zahl mit einfacher Genauigkeit in eine 64`cvtss2si`-Bit-Anweisung ().

## <a name="syntax"></a>Syntax

```C
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Parameter

*value*\
in Eine `__m128` -Struktur, die Gleit Komma Werte enthält.

## <a name="return-value"></a>Rückgabewert

Eine 64-Bit-Ganzzahl, das Ergebnis der Konvertierung des ersten Gleit Komma Werts in eine ganze Zahl.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_cvtss_si64x`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Das erste Element des-Struktur Werts wird in eine ganze Zahl konvertiert und zurückgegeben. Die Rundungs Steuerungs Bits in MXCSR werden verwendet, um das Rundungs Verhalten zu bestimmen. Der Standard Rundungs Modus ist auf den nächsten Wert gerundet und wird auf die gerade Zahl gerundet, wenn der Dezimalteil 0,5 ist. Da die `__m128` -Struktur ein XMM-Register darstellt, nimmt die systeminterne Funktion einen Wert aus dem XMM-Register und schreibt Sie in den Systemspeicher.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
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

[__m128d](../cpp/m128d.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
