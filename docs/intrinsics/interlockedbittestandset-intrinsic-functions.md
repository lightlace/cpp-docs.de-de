---
title: Systeminterne Funktionen „_interlockedbittestandset“
ms.date: 12/17/2018
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
- _interlockedbittestandset
- _interlockedbittestandset_rel
- _interlockedbittestandset64_HLEAcquire
- _interlockedbittestandset_HLERelease
- _interlockedbittestandset_acq
- _interlockedbittestandset_nf
- _interlockedbittestandset64_cpp
- _interlockedbittestandset64_HLERelease
helpviewer_keywords:
- _interlockedbittestandset intrinsic
- _interlockedbittestandset64 intrinsic
- lock_bts instruction
ms.assetid: b1b7e334-53ea-48cf-ba60-5fa3ef51a1fc
ms.openlocfilehash: 3da533b3cf2ab8f396e4ba284cc0bf921a5c80b5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023203"
---
# <a name="interlockedbittestandset-intrinsic-functions"></a>Systeminterne Funktionen „_interlockedbittestandset“

**Microsoft-spezifisch**

Erzeugen Sie eine Anweisung, die Bit `b` der Adresse `a` untersucht und den aktuellen Wert zurückgibt, bevor er auf 1 gesetzt wird.

## <a name="syntax"></a>Syntax

```
unsigned char _interlockedbittestandset(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLERelease(
   __int64 *a,
   __int64 b
);
```

#### <a name="parameters"></a>Parameter

*a*<br/>
[in] Ein Zeiger auf den zu untersuchenden Speicher.

*b*<br/>
[in] Die zu testende Bitposition.

## <a name="return-value"></a>Rückgabewert

Der Wert des Bits an Position `b`, bevor er festgelegt wird.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_interlockedbittestandset`|x86, ARM, x64|\<intrin.h>|
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM|\<intrin.h>|
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, x64|\<immintrin.h>|
|`_interlockedbittestandset64`|x64|\<intrin.h>|
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|x64|\<immintrin.h>|

## <a name="remarks"></a>Hinweise

Auf X86 und X64-Prozessoren, verwenden diese systeminternen Funktionen die `lock bts` Anweisung zum Lesen und des angegebenen Bits auf 1 festgelegt. Der Vorgang ist atomarisch.

Verwenden Sie auf ARM-Prozessoren die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts. Die systeminternen ARM-Funktionen mit dem Suffix `_nf` („no fence“) dienen nicht als Arbeitsspeicherbarriere.

Auf Intel-Prozessoren, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann. Wenn diese systeminternen Funktionen auf Prozessoren aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)