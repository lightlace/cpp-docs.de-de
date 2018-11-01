---
title: __readcr3
ms.date: 11/04/2016
f1_keywords:
- __readcr3
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
ms.openlocfilehash: 928be5798c972881015d9af3733b5757afbf64ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447917"
---
# <a name="readcr3"></a>__readcr3

**Microsoft-spezifisch**

Liest das CR3-Register und den Wert zurückgibt.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __readcr3(void);
```

## <a name="return-value"></a>Rückgabewert

Der Wert im Register CR3.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readcr3`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)