---
title: __ull_rshift
ms.date: 11/04/2016
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: 5d62ec1526aff595c14a53e9eca43a7a3118c8fa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034523"
---
# <a name="ullrshift"></a>__ull_rshift

**Microsoft-spezifisch**

Verschiebt auf X64 einen 64-Bit-Wert, der durch den ersten Parameter auf der rechten Seite angegeben, um eine Anzahl von Bits, die durch den zweiten Parameter angegeben.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __ull_rshift(
   unsigned __int64 mask, 
   int nBit
);
```

#### <a name="parameters"></a>Parameter

*Maske*<br/>
[in] Der 64-Bit-Ganzzahl-Wert, um nach rechts verschoben werden soll.

*nBit*<br/>
[in] Die Anzahl der zu verschiebenden, modulo 32 auf X86 und modulo 64 auf X64 Bits.

## <a name="return-value"></a>Rückgabewert

Die Maske verschoben werden, indem `nBit` Bits.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Wenn der zweite Parameter größer als 31 auf X86 (63 auf X64),, die Anzahl modulo 32 (64 auf X64) ausgeführt wird ist, um zu bestimmen, die Anzahl der zu verschiebenden Bits. Die `ull` gibt den Namen `unsigned long long (unsigned __int64)`.

## <a name="example"></a>Beispiel

```
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

## <a name="output"></a>Output

```
1
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)