---
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 4561bcb84063f3707825c8ca164867d41500e2db
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221674"
---
# <a name="__nop"></a>__nop

**Microsoft-spezifisch**

Generiert plattformspezifischen Computercode, der keinen Vorgang ausführt.

## <a name="syntax"></a>Syntax

```C
void __nop();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="remarks"></a>Hinweise

Die `__nop` -Funktion entspricht der `NOP` -Computeranweisung. Weitere Informationen zu x86 und x64 finden Sie im Dokument "Intel Architecture Software Developer es Manual, Volume 2: Anweisungs Satz Verweis "auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
