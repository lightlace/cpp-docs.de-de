---
title: __rdtscp
ms.date: 07/11/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: b8a31c6d19cd171cbe909c75a27c2389866bd578
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861111"
---
# <a name="rdtscp"></a>__rdtscp

**Microsoft-spezifisch**

Generiert die `rdtscp` -Anweisung, schreibt `TSC_AUX[31:0`], Arbeitsspeicher und gibt die 64-Bit-Time Stamp Counter (`TSC)` Ergebnis.

## <a name="syntax"></a>Syntax

```
unsigned __int64 __rdtscp(
   unsigned int * Aux
);
```

#### <a name="parameters"></a>Parameter

*Aux*<br/>
[out] Zeiger auf einen Speicherort, der den Inhalt des Registers computerspezifische enthält `TSC_AUX[31:0]`.

## <a name="return-value"></a>Rückgabewert

Eine 64-Bit-Ganzzahl ohne Vorzeichen-Taktanzahl.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Dieser systeminternen Funktion generiert die `rdtscp` Anweisung. Um hardwareunterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 27 `CPUInfo[3] (EDX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0.  Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `rdtscp` -Anweisung, die die Ergebnisse sind unvorhersehbar.

Diese Anweisung wartet, bis alle vorherige Anweisungen ausgeführt und alle vorherigen lädt global sichtbar sind. Allerdings ist es keine Serialisierungs-Anweisung. Finden Sie unter den Intel und AMD-Handbüchern für Weitere Informationen.

Die Bedeutung des Werts in `TSC_AUX[31:0]` auf dem Betriebssystem abhängt.

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

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)