---
title: __inbyte
ms.date: 11/04/2016
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 63d4e9229eb7c5058587975d0ea04696786a9c73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562148"
---
# <a name="inbyte"></a>__inbyte

**Microsoft-spezifisch**

Generiert die `in` -Anweisung, ein Byte Zurückgeben der Port anhand des auslesen `Port`.

## <a name="syntax"></a>Syntax

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der gelesen werden.

## <a name="return-value"></a>Rückgabewert

Das gelesene Byte aus dem angegebenen Port.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)