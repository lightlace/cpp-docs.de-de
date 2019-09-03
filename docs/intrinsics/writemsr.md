---
title: __writemsr
ms.date: 09/02/2019
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: 7819477edb8d4e6b18a1213a73ba67065ea7ff57
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219137"
---
# <a name="__writemsr"></a>__writemsr

**Microsoft-spezifisch**

Generiert die Anweisung zum Schreiben in das Modell`wrmsr`spezifische Register ().

## <a name="syntax"></a>Syntax

```C
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

### <a name="parameters"></a>Parameter

*Sich*\
in Das modellspezifische Register.

*Wert*\
in Der zu schreibende Wert.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writemsr`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Funktion kann nur im Kernel Modus verwendet werden, und diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
