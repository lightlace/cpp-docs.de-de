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
ms.openlocfilehash: 20c583b874c2bdb56affc6a90c8464b82c4824f0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040834"
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