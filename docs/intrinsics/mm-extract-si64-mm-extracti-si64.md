---
title: _mm_extract_si64, _mm_extracti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: e77ca5589ed50a4199921603afec1d9888c6cca5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040211"
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64

**Microsoft-spezifisch**

Generiert die `extrq` Anweisung zum Extrahieren von angegebenen Bits aus die unteren 64 Bits des ersten Arguments.

## <a name="syntax"></a>Syntax

```
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

#### <a name="parameters"></a>Parameter

*Source*<br/>
[in] Ein 128-Bit-Feld mit den Daten in die unteren 64 Bits.

*Sicherheitsbeschreibung*<br/>
[in] Ein 128-Bit-Feld, das das Bitfeld extrahieren beschreibt.

*Länge*<br/>
[in] Eine ganze Zahl, die angibt, die Länge des Felds zu extrahieren.

*Index*<br/>
[in] Eine ganze Zahl, die angibt, den Index des Felds, das Extrahieren

## <a name="return-value"></a>Rückgabewert

Ein 128-Bit-Feld mit dem extrahierte Feld in der unwichtigsten Bits.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Dieser systeminternen Funktion generiert die `extrq` Anweisung zum Extrahieren von Bits aus `Source`. Es gibt zwei Versionen dieser Funktion: `_mm_extracti_si64` ist die sofortige-Version und `_mm_extract_si64` wird nicht sofort.  Jede Version extrahiert aus `Source` ein Bitfeld, das durch seine Länge und den Index des seine niedrigstwertigen Bit definiert. Die Werte der Länge und Index stammen mod 64, daher sowohl -1 und 127 als 63 interpretiert werden. Wenn die Summe aus der (geringere) Index und die Feldlänge (geringere) größer als 64 ist, sind die Ergebnisse nicht definiert. Der Wert 0 (null), für die Feldlänge ist als 64 interpretiert. Wenn der Feldindex für Länge und Bit beide NULL Bits 63:0 von sind `Source` extrahiert werden. Wenn die Länge 0 (null ist), aber der Bit-Index nicht 0 (null ist), sind die Ergebnisse nicht definiert.

In einem Aufruf von _mm_extract_si64 die `Descriptor` enthält den Index in Bits 13:8 und die Länge der Daten, die im Bits-5:0 extrahiert werden soll...

Wenn Sie aufrufen `_mm_extracti_si64` mit Argumenten, dass der Compiler nicht ermitteln kann, werden ganzzahlige Konstanten generiert der Compiler Code aus, um diese Werte in einer XMM-Register pack (`Descriptor`) und Aufrufen `_mm_extract_si64`.

Um zu bestimmen, Hardware-Unterstützung für die `extrq` -Anweisung, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 6 `CPUInfo[2] (ECX)`. Dieses Bit wird 1, wenn die Anweisung unterstützt wird und 0 andernfalls. Wenn Sie Code ausführen, die diese systeminterne Hardware verwendet werden, die nicht unterstützt. die `extrq` -Anweisung, die die Ergebnisse sind unvorhersehbar.

## <a name="example"></a>Beispiel

```
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

Copyright 2007 by Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.

## <a name="see-also"></a>Siehe auch

[_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)