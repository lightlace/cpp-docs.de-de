---
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 837b68ca6ac63587cd43a7e8828777221c677e3c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217152"
---
# <a name="__rdtsc"></a>__rdtsc

**Microsoft-spezifisch**

Generiert die `rdtsc` -Anweisung, die den Zeitstempel des Prozessors zurückgibt. Der Prozessorzeit Stempel zeichnet die Anzahl der Uhrzyklen seit dem letzten Zurücksetzen auf.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Rückgabewert

Eine 64-Bit-Ganzzahl ohne Vorzeichen, die eine Takt Anzahl darstellt.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

Die Interpretation des TSC-Werts in späteren Generationen von Hardware unterscheidet sich von der in früheren Versionen von x64. Weitere Informationen finden Sie in den Hardware Handbüchern.

## <a name="example"></a>Beispiel

```cpp
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
