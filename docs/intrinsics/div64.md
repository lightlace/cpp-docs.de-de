---
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 59c5eae66f9e93cb88f9512e405376f2ef5f1ceb
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858021"
---
# <a name="_div64"></a>_div64

Die `_div64` System intern dividiert eine 64-Bit-Ganzzahl durch eine 32-Bit-Ganzzahl. Der Rückgabewert enthält den Quotienten, und der intrinsische Wert gibt den Rest durch einen Zeiger Parameter zurück. `_div64` ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parameters

*Dividenden* \
in Die zu dividierende 64-Bit-Ganzzahl.

*divisor* \
in Die 32-Bit-Ganzzahl, durch die dividiert wird.

*Rest* - \
vorgenommen Die ganzzahligen 32-Bit-Bits des Restwerts.

## <a name="return-value"></a>Rückgabewert

Die 32 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Die `_div64` systeminterne dividiert die *Dividende* durch *Divisor*. Sie speichert den Rest in der 32-Bit-Ganzzahl, auf die von *Restwerten*verwiesen wird, und gibt die 32 Bits des Quotienten zurück.

Die `_div64` systeminterne Funktion ist ab Visual Studio 2019 RTM verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_udiv64](udiv64.md) \
[Systeminterne Compilerfunktionen](compiler-intrinsics.md)
