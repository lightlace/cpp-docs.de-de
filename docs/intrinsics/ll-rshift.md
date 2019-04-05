---
title: __ll_rshift
ms.date: 11/04/2016
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: e39f8fe797467569077dd24baf49670607915107
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041019"
---
# <a name="llrshift"></a>__ll_rshift

**Microsoft-spezifisch**

Verschiebt einen 64-Bit-Wert angegeben, nach dem ersten Parameter nach rechts um eine Anzahl von Bits, die durch den zweiten Parameter angegeben.

## <a name="syntax"></a>Syntax

```
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>Parameter

*Format*<br/>
[in] Der 64-Bit-Ganzzahl-Wert, um nach rechts verschoben werden soll.

*nBit*<br/>
[in] Die Anzahl der zu verschiebenden, modulo 64 auf X64 und modulo 32 auf X86 Bits.

## <a name="return-value"></a>Rückgabewert

Die Maske verschoben werden, indem `nBit` Bits.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Wenn der zweite Parameter größer als 64 auf X64 (32 auf X86),, die Anzahl modulo-64 (32 auf X86) ausgeführt wird ist, um zu bestimmen, die Anzahl der zu verschiebenden Bits. Die `ll` Präfix gibt an, dass dieser eine Operation auf `long long`, ein anderes für `__int64`, signierten ganzzahligen 64-Bit-Typs.

## <a name="example"></a>Beispiel

```
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>Output

```
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

**Beachten Sie** Wenn `_ull_rshift` wurde verwendet, das MSB des Werts nach rechts verschobene hätte 0 (null), damit das gewünschte Ergebnis nicht bei einem negativen Wert abgerufen werden würde.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)