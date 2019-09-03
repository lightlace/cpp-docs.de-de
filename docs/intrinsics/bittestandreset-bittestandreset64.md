---
title: _bittestandreset, _bittestandreset64
ms.date: 09/02/2019
f1_keywords:
- _bittestandreset64_cpp
- _bittestandreset
- _bittestandreset_cpp
- _bittestandreset64
helpviewer_keywords:
- btr instruction
- _bittestandreset intrinsic
- _bittestandreset64 intrinsic
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
ms.openlocfilehash: 9e0c869b926b2f9f3c04fd648f84ef33b8d16fcd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216923"
---
# <a name="_bittestandreset-_bittestandreset64"></a>_bittestandreset, _bittestandreset64

**Microsoft-spezifisch**

Generieren Sie die Anweisung zur unter `b` suchung des Bits `a`der Adresse, geben Sie den aktuellen Wert zurück, und setzen Sie das Bit auf 0 zurück.

## <a name="syntax"></a>Syntax

```C
unsigned char _bittestandreset(
   long *a,
   long b
);
unsigned char _bittestandreset64(
   __int64 *a,
   __int64 b
);
```

### <a name="parameters"></a>Parameter

*ein*\
[in, out] Ein Zeiger auf den zu überprüfenden Arbeitsspeicher.

*b*\
in Die Bitposition, die getestet werden soll.

## <a name="return-value"></a>Rückgabewert

Das Bit an der angegebenen Position.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_bittestandreset`|x86, ARM, x64, ARM64|
|`_bittestandreset64`|x64, ARM64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
// bittestandreset.cpp
// processor: x86, IPF, x64
#include <stdio.h>
#include <limits.h>
#include <intrin.h>

#pragma intrinsic(_bittestandreset)

// Check the sign bit and reset to 0 (taking the absolute value)
// Returns 0 if the number is positive or zero
// Returns 1 if the number is negative
unsigned char absolute_value(long* p)
{
   const int SIGN_BIT = 31;
   return _bittestandreset(p, SIGN_BIT);
}

int main()
{
    long i = -112;
    unsigned char result;

    // Check the sign bit and reset to 0 (taking the absolute value)

    result = absolute_value(&i);
    if (result == 1)
        printf_s("The number was negative.\n");
}
```

```Output
The number was negative.
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
