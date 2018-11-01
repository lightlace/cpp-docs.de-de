---
title: _disable
ms.date: 11/04/2016
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 64e7031ab578632322dfd5c73eb81e0750c1e0b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587810"
---
# <a name="disable"></a>_disable

**Microsoft-spezifisch**

Deaktiviert Unterbrechungen.

## <a name="syntax"></a>Syntax

```
void _disable(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_disable`|X86, ARM, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

`_disable` weist den Prozessor an, das Interrupt-Flag zu deaktivieren. Unter x86-Systemen erzeugt diese Funktion die Anweisung für das Clear Interrupt Flag (`cli`).

Diese Funktion ist nur im Kernelmodus verfügbar. Wenn sie im Benutzermodus verwendet wird, wird zur Laufzeit eine privilegierte Anweisungsausnahme ausgelöst.

Auf ARM-Plattformen ist diese Routine nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)