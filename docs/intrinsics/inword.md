---
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: cfb6e5a11bed5feec3435ab604d22b8f532d3400
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217524"
---
# <a name="__inword"></a>__inword

**Microsoft-spezifisch**

Liest Daten mithilfe der `in` -Anweisung aus dem angegebenen Port.

## <a name="syntax"></a>Syntax

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>Parameter

*Port*\
in Der Port, von dem gelesen werden soll.

## <a name="return-value"></a>Rückgabewert

Das gelesene Wort vom Datentyp.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__inword`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
