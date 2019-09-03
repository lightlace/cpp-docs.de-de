---
title: __stosq
ms.date: 09/02/2019
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 8b347d595da4cdbf1fefb6244940e262981671e9
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219955"
---
# <a name="__stosq"></a>__stosq

**Microsoft-spezifisch**

Generiert eine Speicher Zeichen folgen Anweisung`rep stosq`().

## <a name="syntax"></a>Syntax

```C
void __stosb(
   unsigned __int64* Destination,
   unsigned __int64 Data,
   size_t Count
);
```

### <a name="parameters"></a>Parameter

*Entwickelt*\
vorgenommen Das Ziel des Vorgangs.

*Vorrats*\
in Die Daten, die gespeichert werden sollen.

*Countdown*\
in Die Länge des Blocks der zu schreibenden Quadwords.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosq`|AMD64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, dass die Quadword- *Daten* in einen Block von " *count* Quadwords" in der *Ziel* Zeichenfolge geschrieben werden.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```C
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

```Output
0 ffffffffffff ffffffffffff 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
