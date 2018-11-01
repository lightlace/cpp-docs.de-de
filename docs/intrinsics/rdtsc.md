---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 5f058eaf6587b74f5a75044416d23ac6b64fb415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582064"
---
# <a name="rdtsc"></a>__rdtsc

**Microsoft-spezifisch**

Generiert die `rdtsc` -Anweisung, die den Prozessor Zeitstempel zurückgegeben. Der Zeitstempel für den Prozessor zeichnet die Anzahl der Uhrzyklen seit dem letzten Rücksetzen.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Rückgabewert

Eine 64-Bit-Ganzzahl ohne Vorzeichen, die eine Taktanzahl darstellt.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

Die Interpretation des TSC-Werts in dieser Generation von Hardware unterscheidet sich von dem in früheren Versionen von X64. Finden Sie die Hardware-Handbücher für Weitere Informationen.

## <a name="example"></a>Beispiel

```
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

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)