---
title: __rdtsc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10bf2392d7e469f8f9a8a113b96e0cf2be88a50
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434530"
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