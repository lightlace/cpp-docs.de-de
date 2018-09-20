---
title: __invlpg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01a35d110c56bba6b89c5bf34dedec61bde90794
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403213"
---
# <a name="invlpg"></a>__invlpg

**Microsoft-spezifisch**

Generiert die X86 `invlpg` -Anweisung, die die Translation Lookaside Buffer, TLB (TLB) für die Seite mit dem zugeordneten Speicher verweist erklärt `Address`.

## <a name="syntax"></a>Syntax

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>Parameter

*Adresse*<br/>
[in] Eine 64-Bit-Adresse.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die systeminterne Funktion `__invlpg` eine privilegierte Anweisung ausgibt, und ist nur verfügbar im Kernel-Modus mit einer Berechtigungsstufe (CPL) von 0.

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)