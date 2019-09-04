---
title: _mm_insert_si64, _mm_inserti_si64
ms.date: 09/02/2019
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
ms.openlocfilehash: 08469ad8049df2a07f0e66d650c1ca3118f8b980
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221776"
---
# <a name="_mm_insert_si64-_mm_inserti_si64"></a>_mm_insert_si64, _mm_inserti_si64

**Microsoft-spezifisch**

Generiert die `insertq` Anweisung zum Einfügen von Bits aus dem zweiten Operanden in den ersten Operanden.

## <a name="syntax"></a>Syntax

```C
__m128i _mm_insert_si64(
   __m128i Source1,
   __m128i Source2
);
__m128i _mm_inserti_si64(
   __m128i Source1,
   __m128i Source2
   int Length,
   int Index
);
```

### <a name="parameters"></a>Parameter

*Quelle1*\
in Ein 128-Bit-Feld, das über Eingabedaten in den unteren 64 Bits verfügt, in die ein Feld eingefügt wird.

*Source2*\
in Ein 128-Bit-Feld, das die Daten enthält, die in seine unteren Bits eingefügt werden sollen.  Für `_mm_insert_si64`enthält auch einen Feld Deskriptor in seinen großen Bits.

*Füll*\
in Eine ganzzahlige Konstante, die die Länge des einzufügenden Felds angibt.

*Sin*\
in Eine ganzzahlige Konstante, die den Index des am wenigsten wichtigen Bits des Felds angibt, in das Daten eingefügt werden.

## <a name="return-value"></a>Rückgabewert

Ein 128-Bit-Feld, dessen untere 64 Bits die ursprünglichen niedrigen 64 Bits von *Quelle1*enthalten, wobei das angegebene Bitfeld durch die unteren Bits von *source2*ersetzt wurde. Die oberen 64 Bits des Rückgabewerts sind nicht definiert.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese intrinsie generieren die `insertq` Anweisung zum Einfügen von Bits aus *source2* in *Quelle1*. Es gibt zwei Versionen: `_mm_inserti_si64`, ist die unmittelbare Version und `_mm_insert_si64` ist die nicht unmittelbare Version. Jede Version extrahiert ein Bitfeld mit einer bestimmten Länge aus Source2 und fügt es in Quelle1 ein.  Die extrahierten Bits sind die am wenigsten signifikanten Bits von Source2.  Das Feld Quelle1, in das diese Bits eingefügt werden, wird durch die Länge und den Index des am wenigsten signifikanten Bits definiert.  Die Werte für Länge und Index werden als mod 64 angenommen, sodass sowohl-1 als auch 127 als 63 interpretiert werden. Wenn die Summe des (reduzierten) bitindexes und der (reduzierten) Feldlänge größer als 64 ist, sind die Ergebnisse nicht definiert. Der Wert 0 (null) für die Feldlänge wird als 64 interpretiert. Wenn die Feldlänge und der bitindex NULL sind, werden Bits 63:0 von *source2* in *Quelle1*eingefügt. Wenn die Feldlänge 0 (null) ist, aber der bitindex ungleich 0 (null) ist, sind die Ergebnisse nicht definiert.

Bei einem _mm_insert_si64-Aufrufwert ist die Feldlänge in Bits 77:72 von Source2 und dem Index in Bits 69:64 enthalten.

Wenn Sie mit `_mm_inserti_si64` Argumenten aufzurufen, die der Compiler nicht als ganzzahlige Konstanten ermitteln kann, generiert der Compiler Code, um diese Werte in ein XMM `_mm_insert_si64`-Register zu packen und aufzurufen.

Um die Hardwareunterstützung für die `insertq` -Anweisung zu ermitteln `__cpuid` , müssen `InfoType=0x80000001` Sie die systeminterne Funktion `CPUInfo[2] (ECX)`mit abrufen und Bit 6 von aktivieren. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0. Wenn Sie Code ausführen, der die systeminterne Funktion auf Hardware verwendet, `insertq` die die-Anweisung nicht unterstützt, sind die Ergebnisse unvorhersehbar.

## <a name="example"></a>Beispiel

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source1, source2, source3, result1, result2, result3;

int
main()
{

    __int64 mask;

    source1.ui64[0] = 0xffffffffffffffffll;
    source2.ui64[0] = 0xfedcba9876543210ll;
    source2.ui64[1] = 0xc10;
    source3.ui64[0] = source2.ui64[0];

    result1.m = _mm_insert_si64 (source1.m, source2.m);
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);
    mask = 0xffff << 12;
    mask = ~mask;
    result3.ui64[0] = (source1.ui64[0] & mask) |
                      ((source2.ui64[0] & 0xffff) << 12);

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;

}
```

```Output
result1 = 0xfffffffff3210fff
result2 = 0xfffffffff3210fff
result3 = 0xfffffffff3210fff
```

**Ende Microsoft-spezifisch**

Teile Copyright 2007 von Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Mit Berechtigung von Advanced Micro Devices, Inc.

## <a name="see-also"></a>Siehe auch

[_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
