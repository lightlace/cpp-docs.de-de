---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 0e66bbe978199f47134aa288bdd2bac4eb3e332a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390164"
---
# <a name="udiv128"></a>_udiv128

Die `_udiv128` systeminterne dividiert durch die eine 64-Bit-Ganzzahl ohne Vorzeichen eine 128-Bit-Ganzzahl ohne Vorzeichen. Der Rückgabewert enthält den Quotienten und die systeminterne Funktion gibt den Rest über einen Zeigerparameter. `_udiv128` ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Parameter

*highDividend* \
[in] Die oberen 64 Bits des Divisors.

*lowDividend* \
[in] Die unteren 64 Bits des Divisors.

*divisor* \
[in] Die 64-Bit ganze Zahl, durch die dividiert werden soll.

*remainder* \
[out] Die 64-Bit-Ganzzahl-Bits, der im weiteren Verlauf werden soll.

## <a name="return-value"></a>Rückgabewert

Die 64 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Übergeben Sie die oberen 64 Bits der 128-Bit-Dividende in *HighDividend*, und die unteren 64 Bits *LowDividend*. Die systeminterne Funktion teilt dieses Werts mit *Divisor*. Speichert im weiteren Verlauf in die 64-Bit-Ganzzahl ohne Vorzeichen verweist *Rest*, und die 64 Bits des Quotienten zurückgibt.

Die `_udiv128` systeminterne Funktion ist in Visual Studio 2019 RTM verfügbar ab.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_udiv128`|x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_div128](div128.md) \
[Intrinsische Compilerfunktionen](compiler-intrinsics.md)
