---
title: Intrinsische _InterlockedCompareExchange128-Funktionen
ms.date: 09/02/2019
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
- _InterlockedCompareExchange128_acq
- _InterlockedCompareExchange128_nf
- _InterlockedCompareExchange128_np
- _InterlockedCompareExchange128_rel
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
ms.openlocfilehash: 525b0fd77323789eed05c47c944794ff389bfac5
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217690"
---
# <a name="_interlockedcompareexchange128-intrinsic-functions"></a>Intrinsische _InterlockedCompareExchange128-Funktionen

**Microsoft-spezifisch**

Führt einen Vergleich mit 128-Bit-Interlocked und Exchange aus.

## <a name="syntax"></a>Syntax

```C
unsigned char _InterlockedCompareExchange128(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_acq(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_nf(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_np(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_rel(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
```

### <a name="parameters"></a>Parameter

*Entwickelt*\
[in, out] Ein Zeiger auf das Ziel, bei dem es sich um ein Array von ganzen Zahlen mit 2 64 Bit handelt, die als 128-Bit-Feld angesehen werden. Die Zieldaten müssen eine 16-Byte-Ausrichtung aufweisen, um einen allgemeinen Schutz Fehler zu vermeiden.

*ExchangeHigh*\
in Eine 64-Bit-Ganzzahl, die mit dem hohen Teil des Ziels ausgetauscht werden kann.

*ExchangeLow*\
in Eine 64-Bit-Ganzzahl, die mit dem unteren Teil des Ziels ausgetauscht werden kann.

*ComparandResult*\
[in, out] Ein Zeiger auf ein Array von 2 64-Bit-Ganzzahlen (als 128-Bit-Feld angesehen), das mit dem Ziel verglichen werden soll.  Bei der Ausgabe wird dieses Array mit dem ursprünglichen Wert des Ziels überschrieben.

## <a name="return-value"></a>Rückgabewert

1, wenn der 128-Bit-Comparand dem ursprünglichen Wert des Ziels gleicht. `ExchangeHigh`und `ExchangeLow` das 128-Bit-Ziel überschreiben.

0, wenn der comparand-Wert nicht mit dem ursprünglichen Wert des Ziels übereinstimmt. Der Wert des Ziels ist unverändert, und der Wert von comparand wird mit dem Wert des Ziels überschrieben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_InterlockedCompareExchange128`|x64, ARM64|
|`_InterlockedCompareExchange128_acq`, `_InterlockedCompareExchange128_nf`, `_InterlockedCompareExchange128_rel`|ARM64|
|`_InterlockedCompareExchange128_np`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Der `_InterlockedCompareExchange128` systeminterne generiert `cmpxchg16b` die-Anweisung ( `lock` mit dem Präfix), um einen 128-Bit-gesperrten Vergleich und Exchange auszuführen. Frühe Versionen von AMD 64-Bit-Hardware unterstützen diese Anweisung nicht. Um die Hardwareunterstützung für die `cmpxchg16b` Anweisung zu überprüfen, wenden Sie die `__cpuid` systeminterne mit `InfoType=0x00000001 (standard function 1)`an. Bit 13 von `CPUInfo[2]` (ECX) ist 1, wenn die Anweisung unterstützt wird.

> [!NOTE]
> Der Wert von `ComparandResult` wird immer überschrieben. Nach der `lock` Anweisung kopiert diese systeminterne Funktion sofort den Anfangswert `Destination` von `ComparandResult`in. Aus diesem Grund `ComparandResult` sollten und `Destination` auf separate Speicherorte zeigen, um unerwartetes Verhalten zu vermeiden.

Obwohl Sie für die `_InterlockedCompareExchange128` Thread Synchronisierung auf niedriger Ebene verwenden können, müssen Sie nicht mehr als 128 Bits synchronisieren, wenn Sie stattdessen kleinere Synchronisierungs Funktionen (z `_InterlockedCompareExchange` . b. die anderen intrinsie) verwenden können. Verwenden `_InterlockedCompareExchange128` Sie, wenn Sie den atomaren Zugriff auf einen 128-Bit-Wert im Arbeitsspeicher verwenden möchten.

Wenn Sie Code ausführen, der die systeminterne Funktion auf Hardware verwendet, `cmpxchg16b` die die-Anweisung nicht unterstützt, sind die Ergebnisse unvorhersehbar.

Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel` für Semantiken zum Abrufen bzw. Freigeben, z. B. am Beginn und am Ende eines kritischen Abschnitts. Die systeminternen Arm-Funktionen `_nf` mit dem Suffix ("No fence") fungieren nicht als Arbeitsspeicher Barriere.

Die systeminternen Funktionen mit dem Suffix `_np` („no prefetch“) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

In diesem Beispiel `_InterlockedCompareExchange128` wird verwendet, um das hohe Wort eines Arrays von 2 64-Bit-Ganzzahlen durch die Summe seiner hohen und niedrigen Wörter zu ersetzen und um das niedrige Wort zu erhöhen. Der Zugriff auf das `BigInt.Int` Array ist atomarisch, aber in diesem Beispiel wird ein einzelner Thread verwendet, und die Sperre wird aus Gründen der Einfachheit ignoriert.

```cpp
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


## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Intrinsische _InterlockedCompareExchange-Funktionen](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)\
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
