---
title: __getcallerseflags
ms.date: 09/02/2019
f1_keywords:
- _getcallerseflags
- _getcallerseflags_cpp
helpviewer_keywords:
- _getcallerseflags intrinsic
ms.assetid: 2386596f-33aa-4cc7-b026-5a834637270a
ms.openlocfilehash: d6279db10ec38da7482b26e19e31f2d34dd48a07
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222168"
---
# <a name="__getcallerseflags"></a>__getcallerseflags

**Microsoft-spezifisch**

Gibt den EFLAGS-Wert aus dem Kontext des Aufrufers zurück.

## <a name="syntax"></a>Syntax

```C
unsigned int __getcallerseflags(void);
```

## <a name="return-value"></a>Rückgabewert

EFLAGS-Wert aus dem Kontext des Aufrufers.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__getcallerseflags`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
// getcallerseflags.cpp
// processor: x86, x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__getcallerseflags)

unsigned int g()
{
    unsigned int EFLAGS = __getcallerseflags();
    printf_s("EFLAGS 0x%x\n", EFLAGS);
    return EFLAGS;
}
unsigned int f()
{
    return g();
}

int main()
{
    unsigned int i;
    i = f();
    i = g();
    return 0;
}
```

```Output
EFLAGS 0x202
EFLAGS 0x206
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
