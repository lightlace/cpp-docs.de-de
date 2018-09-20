---
title: _InterlockedCompareExchange128 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs:
- C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dfcdb0c7c2f6315ea7560c236c36d1a1ba449b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389277"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128

**Microsoft-spezifisch**

Führt einen ineinandergreifenden Vergleich 128-Bit- und Exchange.

## <a name="syntax"></a>Syntax

```
unsigned char _InterlockedCompareExchange128(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
```

#### <a name="parameters"></a>Parameter

*Ziel*<br/>
[in, out] Zeiger auf das Ziel, das ein Array von zwei 64-Bit-Ganzzahlen ist, gelten als ein 128-Bit-Feld. Die Zieldaten muss 16-Byte-ausgerichtet werden, um eine allgemeine schutzverletzung zu vermeiden.

*ExchangeHigh*<br/>
[in] Eine 64-Bit-Ganzzahl, die mit der obere Bereich des Ziels ausgetauscht werden kann.

*ExchangeLow*<br/>
[in] Eine 64-Bit-Ganzzahl, die mit den unteren Teil des Ziels ausgetauscht werden kann.

*ComparandResult*<br/>
[in, out] Zeiger auf ein Array von zwei 64-Bit-Ganzzahlen (angesehen als 128-Bit-Feld), mit dem Ziel verglichen werden soll.  Bei der Ausgabe wird dies durch den ursprünglichen Wert des Ziels überschrieben.

## <a name="return-value"></a>Rückgabewert

1, wenn der 128-Bit-comparand-Parameter den ursprünglichen Wert des Ziels entspricht. `ExchangeHigh` und `ExchangeLow` 128-Bit-Ziel zu überschreiben.

0, wenn das zu vergleichende Objekt nicht den ursprünglichen Wert des Ziels entspricht. Der Wert des Ziels unverändert, und der Wert der comparand-Parameter wird mit dem Wert, der das Ziel überschrieben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_InterlockedCompareExchange128`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Dieser systeminternen Funktion generiert die `cmpxchg16b` Anweisung (mit der `lock` Präfix) eine 128-Bit-gesperrten-Vergleichs- und Austauschvorgang ausführen. Frühe Versionen von AMD 64-Bit-Hardware unterstützen diese Anweisung nicht. Zum Prüfen der Hardware-Unterstützung für die `cmpxchg16b` -Anweisung, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x00000001 (standard function 1)`. Teil 13 `CPUInfo[2]` ("ECX") ist 1, wenn die Anweisung unterstützt wird.

> [!NOTE]
>  Der Wert des `ComparandResult` wird immer überschrieben. Nach der `lock` dieser systeminternen Funktion-Anweisung kopiert sofort den Anfangswert des `Destination` zu `ComparandResult`. Aus diesem Grund `ComparandResult` und `Destination` sollte auf unterschiedliche Speicherorte zum Vermeiden von unerwartetem Verhalten verweisen.

Sie können zwar `_InterlockedCompareExchange128` für die Low-Level-Threadsynchronisierung, Sie müssen nicht mehr als 128 Bit zu synchronisieren, wenn Sie kleinere Synchronisierungsfunktionen verwenden können (z. B. die andere `_InterlockedCompareExchange` systeminterne Funktionen) stattdessen. Verwendung `_InterlockedCompareExchange128` Wunsch atomischen Zugriff auf einen 128-Bit-Wert im Arbeitsspeicher.

Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `cmpxchg16b` -Anweisung, die die Ergebnisse sind unvorhersehbar.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

Dieses Beispiel verwendet `_InterlockedCompareExchange128` das hohe Word der ein Array von zwei 64-Bit-Ganzzahlen durch die Summe der hohen und niedrigen Wörter zu ersetzen und das niedrige Word erhöht. Der Zugriff auf das Array BigInt.Int ist atomar, aber in diesem Beispiel verwendet einen einzelnen Thread und ignoriert das Sperren aus Gründen der Einfachheit.

```
// cmpxchg16b.c
// processor: x64
// compile with: /EHsc /O2
#include <stdio.h>
#include <intrin.h>

typedef struct _LARGE_INTEGER_128 {
    __int64 Int[2];
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;

volatile LARGE_INTEGER_128 BigInt;

// This AtomicOp() function atomically performs:
//   BigInt.Int[1] += BigInt.Int[0]
//   BigInt.Int[0] += 1
void AtomicOp ()
{
    LARGE_INTEGER_128 Comparand;
    Comparand.Int[0] = BigInt.Int[0];
    Comparand.Int[1] = BigInt.Int[1];
    do {
        ; // nothing
    } while (_InterlockedCompareExchange128(BigInt.Int,
                                            Comparand.Int[0] + Comparand.Int[1],
                                            Comparand.Int[0] + 1,
                                            Comparand.Int) == 0);
}

// In a real application, several threads contend for the value
// of BigInt.
// Here we focus on the compare and exchange for simplicity.
int main(void)
{
   BigInt.Int[1] = 23;
   BigInt.Int[0] = 11;
   AtomicOp();
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",
      BigInt.Int[1],BigInt.Int[0]);
}
```

```Output
BigInt.Int[1] = 34, BigInt.Int[0] = 12
```

**Ende Microsoft-spezifisch**

Copyright 2007 erweiterten Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Intrinsische Funktionen „_InterlockedCompareExchange“](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)<br/>
[Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)