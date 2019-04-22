---
title: __invlpg
ms.date: 11/04/2016
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: b4f941baae9f03ed288a99d59e2b06262962e339
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023313"
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

*Address*<br/>
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