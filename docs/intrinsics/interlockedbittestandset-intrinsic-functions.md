---
title: intrinsische _interlockedbittestandset-Funktionen
ms.date: 09/02/2019
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
- _interlockedbittestandset64_acq
- _interlockedbittestandset64_nf
- _interlockedbittestandset64_rel
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
ms.openlocfilehash: 9679abf674b5ef366818e73504c3c8c80c5d8ed7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217757"
---
# <a name="_interlockedbittestandset-intrinsic-functions"></a>intrinsische _interlockedbittestandset-Funktionen

**Microsoft-spezifisch**

Generieren Sie eine Anweisung, die `b` das Bit der `a` Adresse untersucht und den aktuellen Wert zurückgibt, bevor Sie es auf 1 festlegen.

## <a name="syntax"></a>Syntax

```C
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
unsigned char _interlockedbittestandset64_acq(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_nf(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_rel(
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

### <a name="parameters"></a>Parameter

*ein*\
in Ein Zeiger auf den zu überprüfenden Arbeitsspeicher.

*b*\
in Die Bitposition, die getestet werden soll.

## <a name="return-value"></a>Rückgabewert

Der Wert des Bits an der Position `b` , bevor Sie festgelegt wird.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_interlockedbittestandset`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM, ARM64|\<intrin.h>|
|`_interlockedbittestandset64_acq`, `_interlockedbittestandset64_nf`, `_interlockedbittestandset64_rel`|ARM64|\<intrin.h>|
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, x64|\<immintrin.h>|
|`_interlockedbittestandset64`|x64, ARM64|\<intrin.h>|
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|x64|\<immintrin.h>|

## <a name="remarks"></a>Hinweise

Auf x86-und x64-Prozessoren verwenden diese systeminternen `lock bts` Funktionen die-Anweisung, um das angegebene Bit zu lesen und auf 1 festzulegen. Der Vorgang ist atomarisch.

Verwenden Sie auf Arm-und ARM64-Prozessoren die System `_acq` internen `_rel` Funktionen mit den Suffixen und zum Abrufen und Freigeben der Semantik, z. b. am Anfang und Ende eines kritischen Abschnitts. Die systeminternen Arm-Funktionen `_nf` mit dem Suffix ("No fence") fungieren nicht als Arbeitsspeicher Barriere.

Auf Intel-Prozessoren, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann. Wenn diese systeminternen Funktionen auf Prozessoren aufgerufen werden, die hle nicht unterstützen, wird der Hinweis ignoriert.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
