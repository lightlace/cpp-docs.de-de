---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: b0033b0e3a62a16c2856b0e25daeebdb5df0c81f
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220386"
---
# <a name="nop"></a>__nop

**Microsoft-spezifisch**

Generiert die plattformspezifische Computercode, der keinen Vorgang ausführt.

## <a name="syntax"></a>Syntax

```
void __nop();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__nop`|X86, ARM, X64, ARM64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="remarks"></a>Hinweise

Die `__nop` -Funktion entspricht der `NOP` -Computeranweisung. Für Weitere Informationen zu X86- und X64, suchen Sie nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference,"auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
