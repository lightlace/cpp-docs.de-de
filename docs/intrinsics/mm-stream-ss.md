---
title: _mm_stream_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 76c6c848351df773b9857b2f83726b64db982d9f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031196"
---
# <a name="mmstreamss"></a>_mm_stream_ss

**Microsoft-spezifisch**

Schreibt 32-Bit-Daten an einem Speicherort, ohne die Caches zu entwickeln.

## <a name="syntax"></a>Syntax

```
void _mm_stream_ss(
   float * Dest,
   __m128 Source
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Ein Zeiger auf den Speicherort, in denen die Quelldaten geschrieben werden.

*Quelle*<br/>
[in] Eine 128-Bit-Zahl, die enthält die `float` Wert, der in der unteren 32 Bits geschrieben werden...

## <a name="return-value"></a>Rückgabewert

Keine

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Dieser systeminternen Funktion generiert die `movntss` Anweisung. Um hardwareunterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 6 `CPUInfo[2] (ECX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0.

Wenn Sie Code ausführen, verwendet der `_mm_stream_ss` syteminternen Funktion bei Hardware, die nicht unterstützt. die `movntss` -Anweisung, die die Ergebnisse sind unvorhersehbar.

## <a name="example"></a>Beispiel

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**Ende Microsoft-spezifisch**

Copyright 2007 by Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.

## <a name="see-also"></a>Siehe auch

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)<br/>
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)<br/>
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)