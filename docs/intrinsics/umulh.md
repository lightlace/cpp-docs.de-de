---
title: __umulh
ms.date: 09/02/2019
f1_keywords:
- __umulh
helpviewer_keywords:
- __umulh intrinsic
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
ms.openlocfilehash: bf098657d1bd5b7ef8a4ffc21f487d2ce619a04e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219668"
---
# <a name="__umulh"></a>__umulh

**Microsoft-spezifisch**

Gibt die oberen 64 Bits des Produkts von zwei 64-Bit-Ganzzahlen ohne Vorzeichen zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __umulh(
   unsigned __int64 a,
   unsigned __int64 b
);
```

### <a name="parameters"></a>Parameter

*ein*\
[in] Die erste zu multiplizierende Zahl.

*b*\
[in] Die zweite zu multiplizierende Zahl.

## <a name="return-value"></a>Rückgabewert

Die oberen 64 Bits de 128-Bit-Ergebnisses der Multiplikation.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__umulh`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="example"></a>Beispiel

```cpp
// umulh.cpp
// processor: X64
#include <cstdio>
#include <intrin.h>

int main()
{
    unsigned __int64 i = 0x10;
    unsigned __int64 j = 0xFEDCBA9876543210;
    unsigned __int64 k = i * j; // k has the low 64 bits
                                // of the product.
    unsigned __int64 result;
    result = __umulh(i, j); // result has the high 64 bits
                            // of the product.
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);
    return 0;
}
```

```Output
0x10 * 0xfedcba9876543210 = 0xfedcba98765432100
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
