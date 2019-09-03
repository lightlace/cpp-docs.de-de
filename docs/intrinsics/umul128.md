---
title: _umul128
ms.date: 09/02/2019
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: 205f0f7f9046ede624bb09e18d8ede32fadbc3de
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219691"
---
# <a name="_umul128"></a>_umul128

**Microsoft-spezifisch**

Multipliziert zwei 64-Bit-Ganzzahlen ohne Vorzeichen, die als die ersten beiden Argumente übergeben wurden, und setzt die oberen 64 Bits des Produkts in die 64-Bit-Ganzzahl ohne Vorzeichen, auf die `HighProduct` verweist, und gibt die unteren 64 Bits des Produkts zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 _umul128(
   unsigned __int64 Multiplier,
   unsigned __int64 Multiplicand,
   unsigned __int64 *HighProduct
);
```

### <a name="parameters"></a>Parameter

*Oren*\
in Die erste zu multiplizierende 64-Bit-Ganzzahl.

*Multiplikand*\
in Die zweite zu multiplizierende 64-Bit-Ganzzahl.

*HighProduct*\
vorgenommen Die hohen 64 Bits des Produkts.

## <a name="return-value"></a>Rückgabewert

Die unteren 64 Bits des Produkts.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_umul128`|x64|\<intrin.h>|

## <a name="example"></a>Beispiel

```C
// umul128.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_umul128)

int main()
{
    unsigned __int64 a = 0x0fffffffffffffffI64;
    unsigned __int64 b = 0xf0000000I64;
    unsigned __int64 c, d;

    d = _umul128(a, b, &c);

    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
