---
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 4dcabd6ed0f7fb3f422927815cbdc91f2b4b9d43
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221320"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft-spezifisch**

Generiert die `rdtscp` -Anweisung, `TSC_AUX[31:0`schreibt] in den Arbeitsspeicher und gibt den 64-Bit-Zeit`TSC)` Stempel (result) zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>Parameter

*BODA*\
vorgenommen Ein Zeiger auf einen Speicherort, der den Inhalt des computerspezifischen Registers `TSC_AUX[31:0]`enthält.

## <a name="return-value"></a>Rückgabewert

Eine 64-Bit-Ganzzahl ohne Vorzeichen.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `__rdtscp` systeminterne Generierung `rdtscp` generiert die-Anweisung. Um die Hardwareunterstützung für diese Anweisung zu ermitteln, `__cpuid` müssen Sie `InfoType=0x80000001` die systeminterne Funktion mit `CPUInfo[3] (EDX)`und das Bit 27 von abrufen. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0.  Wenn Sie Code ausführen, der die systeminterne Funktion auf Hardware verwendet, `rdtscp` die die-Anweisung nicht unterstützt, sind die Ergebnisse unvorhersehbar.

Diese Anweisung wartet, bis alle vorherigen Anweisungen ausgeführt wurden und alle vorherigen Auslastungen Global sichtbar sind. Es handelt sich jedoch nicht um eine serialisierende Anweisung. Weitere Informationen finden Sie unter den Intel-und AMD-Handbüchern.

Die Bedeutung des Werts in `TSC_AUX[31:0]` hängt vom Betriebssystem ab.

## <a name="example"></a>Beispiel

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__rdtsc](../intrinsics/rdtsc.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
