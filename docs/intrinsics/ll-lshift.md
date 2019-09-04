---
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 158ecbf39320d70b51f1f498a0b689ba58fec363
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221821"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Microsoft-spezifisch**

Verschiebt den angegebenen 64-Bit-Wert um die angegebene Anzahl von Bits nach links.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Parameter

*Chel*\
in Der ganzzahlige ganzzahlige 64-Bit-Wert.

*nBit*\
in Die Anzahl der zu Verschiebungs enden Bits.

## <a name="return-value"></a>Rückgabewert

Die Maske wurde von Bits `nBit` nach links verschoben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Wenn Sie das Programm für die 64-Bit-Architektur kompilieren und `nBit` größer als 63 ist, ist `nBit` die Anzahl der zu Verschiebe Bits modulo 64. Wenn Sie das Programm für die 32-Bit-Architektur kompilieren und `nBit` größer als 31 ist, ist `nBit` die Anzahl der zu Verschiebe Bits modulo 32.

Der `ll` im Namen gibt an, dass es sich um einen `long long` Vorgang`__int64`auf () handelt.

## <a name="example"></a>Beispiel

```cpp
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>Ausgabe

```Output
10000
```

> [!NOTE]
> Es ist keine unsignierte Version des Left Shift-Vorgangs vorhanden. Der Grund hierfür `__ll_lshift` ist, dass bereits einen nicht signierten Eingabeparameter verwendet. Anders als bei der rechten Schicht gibt es keine Vorzeichen Abhängigkeit für die linke Schicht, da das unwichtigste Bit im Ergebnis immer auf 0 (null) festgelegt ist, unabhängig vom Vorzeichen des verschobenen Werts.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__ll_rshift](../intrinsics/ll-rshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
