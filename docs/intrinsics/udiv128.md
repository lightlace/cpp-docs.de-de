---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 5e8cc9ca3dbf19a04d07edb1d73df84f2e29a5c3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857982"
---
# <a name="_udiv128"></a>_udiv128

Die `_udiv128` systeminterne unterteilt eine 128-Bit-Ganzzahl ohne Vorzeichen durch eine 64-Bit-Ganzzahl ohne Vorzeichen. Der Rückgabewert enthält den Quotienten, und der intrinsische Wert gibt den Rest durch einen Zeiger Parameter zurück. `_udiv128` ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Parameters

*highdividende* - \
in Die hohen 64 Bits der Dividende.

*lowDividend* \
in Die unteren 64 Bits der Dividende.

*divisor* \
in Die 64-Bit-Ganzzahl, durch die dividiert wird.

*Rest* - \
vorgenommen Die ganzzahligen 64-Bit-Bits des Restwerts.

## <a name="return-value"></a>Rückgabewert

Die 64 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Übergeben Sie die oberen 64 Bits der 128-Bit-Dividende in *highdividende*und die niedrigeren 64 Bits in *lowdividenden*. Der systeminterne dividiert diesen Wert durch *Divisor*. Er speichert den Rest in der 64-Bit-Ganzzahl ohne Vorzeichen, auf den *Restwert*zeigt, und gibt die 64 Bits des Quotienten zurück.

Die `_udiv128` systeminterne Funktion ist ab Visual Studio 2019 RTM verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_udiv128`|x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_div128](div128.md) \
[Systeminterne Compilerfunktionen](compiler-intrinsics.md)
