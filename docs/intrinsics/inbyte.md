---
title: __inbyte
ms.date: 09/02/2019
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: f0036763ed7315a54fbfe6dcc873b46b52f0730c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222140"
---
# <a name="__inbyte"></a>__inbyte

**Microsoft-spezifisch**

Generiert die `in` -Anweisung und gibt ein einzelnes Byte zurück, das von dem `Port`durch angegebenen Port gelesen wird.

## <a name="syntax"></a>Syntax

```C
unsigned char __inbyte(
   unsigned short Port
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, von dem gelesen werden soll.

## <a name="return-value"></a>Rückgabewert

Das aus dem angegebenen Port gelesene Byte.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
