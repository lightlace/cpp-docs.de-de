---
title: _mm_stream_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_si64x
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
ms.openlocfilehash: 9e93fb5e6e9a9ad926a13a4b69c1dddbfb55f2f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431251"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Microsoft-spezifisch**

Generiert die MOVNTI-Anweisung. Schreibt die Daten in `Source` auf einen Speicherbereich durch angegebene `Dest`, ohne die Caches zu entwickeln.

## <a name="syntax"></a>Syntax

```
void _mm_stream_si64x( 
   __int64 * Dest, 
   __int64 Source 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Ein Zeiger auf den Speicherort die Quelldaten zu schreiben.

*Quelle*<br/>
[in] Die Daten geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_mm_stream_si64x`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)