---
title: Intrinsische _InterlockedExchangePointer-Funktionen
ms.date: 09/02/2019
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
ms.openlocfilehash: 1402dcf5279658c1364b59a324d988129bc841d8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217633"
---
# <a name="_interlockedexchangepointer-intrinsic-functions"></a>Intrinsische _InterlockedExchangePointer-Funktionen

**Microsoft-spezifisch**

Führt einen atomaren Austausch Vorgang aus, der die als zweites Argument eingeführte Adresse in das erste Argument kopiert und die ursprüngliche Adresse des ersten zurückgibt.

## <a name="syntax"></a>Syntax

```C
void * _InterlockedExchangePointer(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_acq(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_rel(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_nf(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLEAcquire(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLERelease(
   void * volatile * Target,
   void * Value
);
```

### <a name="parameters"></a>Parameter

*Spar*\
[in, out] Zeiger auf den Zeiger auf den zu Austausch Wert. Die-Funktion legt den Wert auf *value* fest und gibt den vorherigen Wert zurück.

*Wert*\
in Der Wert, der mit dem Wert ausgetauscht werden soll, auf den von *target*verwiesen wird.

## <a name="return-value"></a>Rückgabewert

Die-Funktion gibt den Anfangswert zurück, auf den durch *target*verwiesen wird.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_InterlockedExchangePointer`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM, ARM64|\<intrin.h>|
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|x64|\<immintrin.h>|

In der x86-Architektur ist `_InterlockedExchangePointer` ein Makro, das `_InterlockedExchange` aufruft.

## <a name="remarks"></a>Hinweise

Auf einem 64-Bit-System sind die Parameter 64 Bits und müssen an den 64-Bit-Grenzen ausgerichtet sein. Andernfalls schlägt die Funktion fehl. In einem 32-Bit-System sind die Parameter 32 Bits und müssen auf 32-Bit-Grenzen ausgerichtet sein. Weitere Informationen finden Sie unter [Ausrichten](../cpp/align-cpp.md).

Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts. Das systeminterne- `_nf` Suffix mit dem Suffix ("No fence") fungiert nicht als Arbeitsspeicher Barriere.

Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die hle nicht unterstützen, wird der Hinweis ignoriert.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
