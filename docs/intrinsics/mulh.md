---
title: __mulh | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __mulh
dev_langs:
- C++
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9393026814e8f3f7dd90704cd08ea96dfb9a35a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407321"
---
# <a name="mulh"></a>__mulh

**Microsoft-spezifisch**

Gibt die oberen 64 Bits des Produkts von zwei 64-Bit-Ganzzahlen mit Vorzeichen zurück.

## <a name="syntax"></a>Syntax

```
__int64 __mulh( 
   __int64 a, 
   __int64 b 
);
```

#### <a name="parameters"></a>Parameter

*a*<br/>
[in] Die erste zu multiplizierende Zahl.

*b*<br/>
[in] Die zweite zu multiplizierende Zahl.

## <a name="return-value"></a>Rückgabewert

Die oberen 64 Bits de 128-Bit-Ergebnisses der Multiplikation.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__mulh`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// mulh.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__mulh)

int main()
{
    __int64 a = 0x0fffffffffffffffI64;
    __int64 b = 0xf0000000I64;

    __int64 result = __mulh(a, b); // the high 64 bits
    __int64 result2 = a * b; // the low 64 bits

    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",
             a, b, result, result2);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)