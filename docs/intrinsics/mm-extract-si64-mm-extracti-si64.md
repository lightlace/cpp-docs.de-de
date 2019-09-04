---
title: _mm_extract_si64, _mm_extracti_si64
ms.date: 09/02/2019
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: cfd7029966c29f876f0e4f671830e20e2eacc940
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217401"
---
# <a name="_mm_extract_si64-_mm_extracti_si64"></a>_mm_extract_si64, _mm_extracti_si64

**Microsoft-spezifisch**

Generiert die `extrq` Anweisung zum Extrahieren der angegebenen Bits aus den unteren 64 Bits des ersten Arguments.

## <a name="syntax"></a>Syntax

```C
__m128i _mm_extract_si64(
   __m128i Source,
   __m128i Descriptor
);
__m128i _mm_extracti_si64(
   __m128i Source,
   int Length,
   int Index
);
```

### <a name="parameters"></a>Parameter

*Source*\
in Ein 128-Bit-Feld mit Eingabedaten in den unteren 64 Bits.

*Deskriptor*\
in Ein 128-Bit-Feld, das das zu Extra hier ender Bitfeld beschreibt.

*Füll*\
in Eine ganze Zahl, die die Länge des zu extrahierenden Felds angibt.

*Sin*\
in Eine ganze Zahl, die den Index des zu extrahierenden Felds angibt.

## <a name="return-value"></a>Rückgabewert

Ein 128-Bit-Feld mit dem extrahierten Feld in den am wenigsten wichtigen Bits.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese intrinsie generieren die `extrq` Anweisung zum Extrahieren von Bits aus der *Quelle*. Es gibt zwei Versionen: `_mm_extracti_si64` ist die unmittelbare Version und `_mm_extract_si64` ist die nicht unmittelbare Version. Jede Version extrahiert aus der *Quelle* ein Bitfeld, das durch ihre Länge und den Index des am wenigsten wichtigen Bits definiert ist. Die Werte für Länge und Index werden als mod 64 angenommen, sodass sowohl-1 als auch 127 als 63 interpretiert werden. Wenn die Summe des (reduzierten) Indexes und der (reduzierten) Feldlänge größer als 64 ist, sind die Ergebnisse nicht definiert. Der Wert 0 (null) für die Feldlänge wird als 64 interpretiert. Wenn die Feldlänge und der bitindex beide NULL sind, werden Bits 63:0 der *Quelle* extrahiert. Wenn die Feldlänge 0 (null) ist, aber der bitindex ungleich 0 (null) ist, sind die Ergebnisse nicht definiert.

In einem-Aufrufwert `_mm_extract_si64`enthält der *Deskriptor* den Index in Bits 13:8 und die Feldlänge der Daten, die in Bits 5:0 extrahiert werden sollen.

Wenn Sie mit `_mm_extracti_si64` Argumenten aufzurufen, die der Compiler nicht als ganzzahlige Konstanten ermitteln kann, generiert der Compiler Code, mit dem diese Werte in ein XMM-Register ( `_mm_extract_si64`*Deskriptor*) verpackt und aufgerufen werden.

Um die Hardwareunterstützung für die `extrq` -Anweisung zu ermitteln `__cpuid` , müssen `InfoType=0x80000001` Sie die systeminterne Funktion `CPUInfo[2] (ECX)`mit abrufen und Bit 6 von aktivieren. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0. Wenn Sie Code ausführen, der diese systeminterne Hardware verwendet, von `extrq` der die-Anweisung nicht unterstützt wird, sind die Ergebnisse unvorhersehbar.

## <a name="example"></a>Beispiel

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source, descriptor, result1, result2, result3;

int
main()
{
    source.ui64[0] =     0xfedcba9876543210ll;
    descriptor.ui64[0] = 0x0000000000000b1bll;

    result1.m = _mm_extract_si64 (source.m, descriptor.m);
    result2.m = _mm_extracti_si64(source.m, 27, 11);
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;
}
```

```Output
result1 = 0x30eca86
result2 = 0x30eca86
result3 = 0x30eca86
```

**Ende Microsoft-spezifisch**

Teile Copyright 2007 von Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Mit Berechtigung von Advanced Micro Devices, Inc.

## <a name="see-also"></a>Siehe auch

[_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
