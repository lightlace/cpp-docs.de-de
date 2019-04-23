---
title: _div64
ms.date: 04/17/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: a221cc7cf0655a41873c6777aecd8a9b27131b74
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982419"
---
# <a name="div64"></a>_div64

Die `_div64` systeminterne teilt eine 64-Bit-Ganzzahl durch eine 32-Bit-Ganzzahl. Der Rückgabewert enthält den Quotienten und die systeminterne Funktion gibt den Rest über einen Zeigerparameter. `_div64` ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parameter

*dividend* \
[in] Die 64-Bit-Ganzzahl, zu teilen.

*divisor* \
[in] Die 32-Bit ganze Zahl, durch die dividiert werden soll.

*remainder* \
[out] Die 32-Bit-Ganzzahl-Bits, der im weiteren Verlauf werden soll.

## <a name="return-value"></a>Rückgabewert

Die 32 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Die `_div64` systeminterne dividiert *Dividend* von *Divisor*. Speichert den Rest in der 32-Bit-Ganzzahl, die verweist *Rest*, und gibt die 32 Bits des Quotienten zurück.

Die `_div64` systeminterne Funktion ist in Visual Studio 2019 RTM verfügbar ab.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_udiv64](udiv64.md) \
[Intrinsische Compilerfunktionen](compiler-intrinsics.md)
