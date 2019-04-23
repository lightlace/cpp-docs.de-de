---
title: _udiv64
ms.date: 04/17/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 73a29b180eeda49a9a25e9e568d25c7563234fad
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982449"
---
# <a name="udiv64"></a>_udiv64

Die `_udiv64` systeminterne dividiert durch eine 32-Bit-Ganzzahl ohne Vorzeichen eine 64-Bit-Ganzzahl ohne Vorzeichen. Der Rückgabewert enthält den Quotienten und die systeminterne Funktion gibt den Rest über einen Zeigerparameter. `_udiv64` ist **Microsoft-spezifisch**.

## <a name="syntax"></a>Syntax

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Parameter

*dividend*<br/>
[in] Das Aufteilen 64-Bit-Ganzzahl ohne Vorzeichen.

*divisor*<br/>
[in] Die Division durch 32-Bit-Ganzzahl ohne Vorzeichen.

*remainder*<br/>
[out] Der Rest des 32-Bit-Ganzzahl ohne Vorzeichen.

## <a name="return-value"></a>Rückgabewert

Die 32 Bits des Quotienten.

## <a name="remarks"></a>Hinweise

Die `_udiv64` systeminterne dividiert *Dividend* von *Divisor*. Speichert im weiteren Verlauf in die 32-Bit-Ganzzahl ohne Vorzeichen verweist *Rest*, und gibt die 32 Bits des Quotienten zurück.

Die `_udiv64` systeminterne Funktion ist in Visual Studio 2019 RTM verfügbar ab.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Siehe auch

[_div64](div64.md) \
[Intrinsische Compilerfunktionen](compiler-intrinsics.md)
