---
title: __stosq
ms.date: 11/04/2016
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 48c3e8db2683ee190a23974d12d36fbeef6a0094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477466"
---
# <a name="stosq"></a>__stosq

**Microsoft-spezifisch**

Generiert eine Store-Zeichenfolge-Anweisung (`rep stosq`).

## <a name="syntax"></a>Syntax

```
void __stosb( 
   unsigned __int64* Dest, 
   unsigned __int64 Data, 
   size_t Count 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Das Ziel des Vorgangs.

*Data*<br/>
[in] Die zu speichernden Daten.

*Anzahl*<br/>
[in] Die Länge des Blocks des Vierfachwörtern schreiben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosq`|AMD64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, die die Vierfachwort `Data` wird geschrieben, in einen Block von `Count` Vierfachwörtern in die `Dest` Zeichenfolge.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// stosq.c
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosq)

int main()
{
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;
   unsigned __int64 a[10];
   memset(a, 0, sizeof(a));
   __stosq(a+1, val, 2);
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

## <a name="output"></a>Output

```
0 ffffffffffff ffffffffffff 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)