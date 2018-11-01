---
title: __shiftright128
ms.date: 11/04/2016
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: dc72e70de4ba3bf5131044f073a0b5a531eabb0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589266"
---
# <a name="shiftright128"></a>__shiftright128

**Microsoft-spezifisch**

Verschiebt eine 128-Bit-Menge, dargestellt als zwei 64-Bit-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach rechts und gibt die unteren 64 Bits des Ergebnisses zurück.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __shiftright128( 
   unsigned __int64 LowPart, 
   unsigned __int64 HighPart, 
   unsigned char Shift 
);
```

#### <a name="parameters"></a>Parameter

*LowPart*<br/>
[in] Die unteren 64 Bits der zu verschiebenden 128-Bit-Menge.

*HighPart*<br/>
[in] Die oberen 64 Bits der zu verschiebenden 128-Bit-Menge.

*UMSCHALTTASTE*<br/>
[in] Die Anzahl der zu verschiebenden Bits.

## <a name="return-value"></a>Rückgabewert

Die unteren 64 Bits des Ergebnisses.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__shiftright128`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Der `Shift`-Wert ist immer modulo 64. So verschiebt z. B. beim Aufrufen von `__shiftright128(0, 1, 64)` die Funktion die `0`-Bits des oberen Teils nach rechts und gibt einen unteren Teil von `0` und nicht von `1` zurück, wie man annehmen könnte.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter [__shiftleft128](../intrinsics/shiftleft128.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)