---
title: __stosd | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __stosd
dev_langs:
- C++
helpviewer_keywords:
- stosd instruction
- rep stosd instruction
- __stosd intrinsic
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bb0d75cc4af033bf1bc942a918beecf2aedf911
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396141"
---
# <a name="stosd"></a>__stosd

**Microsoft-spezifisch**

Generiert eine Store-Zeichenfolge-Anweisung (`rep stosd`).

## <a name="syntax"></a>Syntax

```
void __stosd( 
   unsigned long* Dest, 
   unsigned long Data, 
   size_t Count 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Das Ziel des Vorgangs.

*Data*<br/>
[in] Die zu speichernden Daten.

*Anzahl*<br/>
[in] Die Länge des Blocks des Doppelwort schreiben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosd`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, das zeigt Doppelwort `Data` wird geschrieben, in einen Block von `Count` die zeigt Doppelwort an der Speicheradresse `Dest`.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// stosd.c
// processor: x86, x64

#include <stdio.h>
#include <memory.h>
#include <intrin.h>

#pragma intrinsic(__stosd)

int main()
{
    unsigned long val = 99999;
    unsigned long a[10];

    memset(a, 0, sizeof(a));
    __stosd(a+1, val, 2);

printf_s( "%u %u %u %u",
              a[0], a[1], a[2], a[3]);
}
```

```Output
0 99999 99999 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)