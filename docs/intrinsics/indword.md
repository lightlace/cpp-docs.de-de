---
title: __indword
ms.date: 11/04/2016
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: f4b37247093da14c8d5e8fed69b01265d3fed2ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599809"
---
# <a name="indword"></a>__indword

**Microsoft-spezifisch**

Liest ein Doppelwort der Daten aus dem angegebenen Port mithilfe der `in` Anweisung.

## <a name="syntax"></a>Syntax

```
unsigned long __indword(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der gelesen werden.

## <a name="return-value"></a>Rückgabewert

Lesen Sie das Wort aus den Port.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__indword`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)