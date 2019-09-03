---
title: __readcr4
ms.date: 09/02/2019
f1_keywords:
- __readcr4
helpviewer_keywords:
- __readcr4 intrinsic
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
ms.openlocfilehash: 4d43b5204d412de40284f89cfd4d74f1c1f9d86d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216732"
---
# <a name="__readcr4"></a>__readcr4

**Microsoft-spezifisch**

Liest das CR4-Register und gibt dessen Wert zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __readcr4(void);
```

## <a name="return-value"></a>Rückgabewert

Der Wert im CR4-Register.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readcr4`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die systeminterne Funktion ist nur im Kernel Modus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
