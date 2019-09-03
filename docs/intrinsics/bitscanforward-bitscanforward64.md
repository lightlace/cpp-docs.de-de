---
title: _BitScanForward, _BitScanForward64
ms.date: 09/02/2019
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 91f43d19259419b78d1910a00a154d2d4f0adfc7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222214"
---
# <a name="_bitscanforward-_bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Microsoft-spezifisch**

Suchen Sie die Maskendaten vom niedrigstwertigen Bit (LSB) bis zum höchstwertigen Bit (MSB) für ein festgelegtes Bit (1).

## <a name="syntax"></a>Syntax

```C
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

### <a name="parameters"></a>Parameter

*Sin*\
vorgenommen Geladen mit der Bitposition des ersten festgelegten Bits (1).

*Chel*\
in Der zu durchsuchende 32-Bit-oder 64-Bit-Wert.

## <a name="return-value"></a>Rückgabewert

0, wenn die Maske null ist; andernfalls ungleich null.

## <a name="remarks"></a>Hinweise

Wenn ein festgelegtes Bit gefunden wird, wird die Bitposition des ersten festgelegten gefundenen Bits in den ersten Parameter zurückgegeben. Wenn kein festgelegtes Bit gefunden wird, wird 0 zurückgegeben; andernfalls wird 1 zurückgegeben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64, ARM64|
|`_BitScanForward64`|ARM64, x64|

**Header Datei** \<intrin. h->

## <a name="example"></a>Beispiel

```cpp
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

```Input
12
```

```Output
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
