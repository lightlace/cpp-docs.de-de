---
title: _bittest, _bittest64
ms.date: 11/04/2016
f1_keywords:
- _bittest64
- _bittest_cpp
- _bittest64_cpp
- _bittest
helpviewer_keywords:
- _bittest intrinsic
- _bittest64 intrinsic
- bt instruction
ms.assetid: 15e62afb-abea-4ee7-a6b1-13efa2034937
ms.openlocfilehash: 1d29b8bec646bb2da8acfe20479fe0e238db0de5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035227"
---
# <a name="bittest-bittest64"></a>_bittest, _bittest64

**Microsoft-spezifisch**

Generiert die `bt`-Anweisung, die das Bit an Position `b` der Adresse `a` untersucht, und gibt den Wert dieses Bits zurück.

## <a name="syntax"></a>Syntax

```
unsigned char _bittest(
   long const *a,
   long b
);
unsigned char _bittest64(
   __int64 const *a,
   __int64 b
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
[in] Ein Zeiger auf den zu untersuchenden Speicher.

*b*<br/>
[in] Die zu testende Bitposition.

### <a name="return-value"></a>Rückgabewert

Das Bit an der angegebenen Position.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_bittest`|x86, ARM, x64|\<intrin.h>|
|`_bittest64`|ARM, x64|\<intrin.h>|

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
// bittest.cpp
// processor: x86, ARM, x64

#include <stdio.h>
#include <intrin.h>

long num = 78002;

int main()
{
    unsigned char bits[32];
    long nBit;

    printf_s("Number: %d\n", num);

    for (nBit = 0; nBit < 31; nBit++)
    {
        bits[nBit] = _bittest(&num, nBit);
    }

    printf_s("Binary representation:\n");
    while (nBit--)
    {
        if (bits[nBit])
            printf_s("1");
        else
            printf_s("0");
    }
}
```

```Output
Number: 78002
Binary representation:
0000000000000010011000010110010
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)