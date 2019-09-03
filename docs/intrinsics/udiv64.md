---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 6dabbc94260ef578eb1a58a1b289b4a4654decdd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219679"
---
# <a name="_udiv64"></a>_udiv64

Die `_udiv64` systeminterne dividiert eine 64-Bit-Ganzzahl ohne Vorzeichen durch eine 32-Bit-Ganzzahl ohne Vorzeichen. Der Rückgabewert enthält den Quotienten, und der intrinsische Wert gibt den Rest durch einen Zeiger Parameter zurück. `_udiv64`ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Parameter

*Dividend*\
in Die zu dividierende 64-Bit-Ganzzahl ohne Vorzeichen.

*divisor*\
in Die 32-Bit-Ganzzahl ohne Vorzeichen, durch die dividiert wird.

*ergibt*\
vorgenommen Die 32-Bit-Ganzzahl ohne Vorzeichen (Rest).

## <a name="return-value"></a>Rückgabewert

Die 32 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Die `_udiv64` systeminterne dividiert die *Dividende* durch *Divisor*. Er speichert den Rest in der 32-Bit-Ganzzahl ohne Vorzeichen,auf den Restwert zeigt, und gibt die 32 Bits des Quotienten zurück.

Die `_udiv64` systeminterne Funktion ist ab Visual Studio 2019 RTM verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_div64](div64.md) \
[Systeminterne Compilerfunktionen](compiler-intrinsics.md)
