---
title: _disable
ms.date: 09/02/2019
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 94be850e1d494ff62df84922b46f28481be68314
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216819"
---
# <a name="_disable"></a>_disable

**Microsoft-spezifisch**

Deaktiviert Unterbrechungen.

## <a name="syntax"></a>Syntax

```C
void _disable(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_disable`|x86, ARM, x64, ARM64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

`_disable` weist den Prozessor an, das Interrupt-Flag zu deaktivieren. Unter x86-Systemen erzeugt diese Funktion die Anweisung für das Clear Interrupt Flag (`cli`).

Diese Funktion ist nur im Kernelmodus verfügbar. Wenn sie im Benutzermodus verwendet wird, wird zur Laufzeit eine privilegierte Anweisungsausnahme ausgelöst.

Auf Arm-und ARM64-Plattformen ist diese Routine nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
