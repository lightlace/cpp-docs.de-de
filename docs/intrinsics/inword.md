---
title: __inword
ms.date: 11/04/2016
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 85498fd85f5401ad123794cc9aaed2b278db867c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475360"
---
# <a name="inword"></a>__inword

**Microsoft-spezifisch**

Liest Daten aus den angegebenen Port mit der `in` Anweisung.

## <a name="syntax"></a>Syntax

```
unsigned short __inword(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der gelesen werden.

## <a name="return-value"></a>Rückgabewert

Das Wort gelesenen Daten.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inword`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)