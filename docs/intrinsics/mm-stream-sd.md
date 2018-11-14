---
title: _mm_stream_sd
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: cf57d485ab3dd268d217b2ef44ff53bcec3d2e63
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518137"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Microsoft-spezifisch**

Schreibt 64-Bit-Daten an einem Speicherort, ohne die Caches zu entwickeln.

## <a name="syntax"></a>Syntax

```
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Ein Zeiger auf den Speicherort, in denen die Quelldaten geschrieben wird.

*Quelle*<br/>
[in] Eine 128-Bit-Wert, der `double` Wert, der in der unteren 64 Bits geschrieben werden...

## <a name="return-value"></a>Rückgabewert

Keine

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Dieser systeminternen Funktion generiert die `movntsd` Anweisung. Um hardwareunterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 6 `CPUInfo[2] (ECX)`. Dieses Bit ist 1, wenn die Hardware diese Anweisung, und 0 unterstützt.

Wenn Sie Code ausführen, verwendet der `_mm_stream_sd` syteminternen Funktion bei Hardware, die nicht unterstützt. die `movntsd` -Anweisung, die die Ergebnisse sind unvorhersehbar.

## <a name="example"></a>Beispiel

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128d vals;
    double d[2];

    d[0] = -1.;
    d[1] = -2.;
    vals.m128d_f64[0] = 0.;
    vals.m128d_f64[1] = 1.;
    _mm_stream_sd(&d[1], vals);
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;
}
```

```Output
d[0] = -1, d[1] = 1
```

**Ende Microsoft-spezifisch**

Copyright 2007 erweiterten Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.

## <a name="see-also"></a>Siehe auch

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)<br/>
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)