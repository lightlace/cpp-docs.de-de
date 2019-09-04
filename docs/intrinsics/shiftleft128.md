---
title: __shiftleft128
ms.date: 09/02/2019
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: 5da9ac81cedbdd24e10eb438892f88510c32ca24
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218006"
---
# <a name="__shiftleft128"></a>__shiftleft128

**Microsoft-spezifisch**

Verschiebt eine 128-Bit-Menge, dargestellt als zwei 64-Bit-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach links und gibt die unteren 64 Bits des Ergebnisses zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __shiftleft128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parameter

*LowPart*\
in Die unteren 64 Bits der zu Verschiebungs enden 128-Bit-Menge.

*HighPart*\
in Die hohen 64 Bits der 128-Bit-Menge, die verschoben werden soll.

*Schuss*\
in Die Anzahl der zu Verschiebungs enden Bits.

## <a name="return-value"></a>Rückgabewert

Die oberen 64 Bits des Ergebnisses.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__shiftleft128`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Der *Verschiebungs* Wert ist immer modulo 64. Wenn Sie z. `__shiftleft128(1, 0, 64)`b. aufzurufen, `0` verschiebt die Funktion die unteren Teile der Bits nach links und gibt einen großen `0` Teil von `1` und nicht wie erwartet aus.

## <a name="example"></a>Beispiel

```C
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__shiftright128](../intrinsics/shiftright128.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
