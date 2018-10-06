---
title: __nop | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __nop
dev_langs:
- C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc5dab4ba2c23f60eb4407548cea5c15106c1401
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820502"
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
|`__nop`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="remarks"></a>Hinweise

Die `__nop` -Funktion ist gleichbedeutend mit der `NOP` computeranweisung. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)