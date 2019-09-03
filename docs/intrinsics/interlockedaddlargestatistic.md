---
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: de8c5b7dfd2462dddcb98324ebacc44c8148d85e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222090"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft-spezifisch**

Führt eine Interlocked-Addition aus, bei der der erste Operand ein 64-Bit-Wert ist.

## <a name="syntax"></a>Syntax

```C
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

### <a name="parameters"></a>Parameter

*Addend*\
[in, out] Ein Zeiger auf den ersten Operanden für den Add-Vorgang. Der Wert, auf den verweist, wird durch das Ergebnis der Addition ersetzt.

*Wert*\
in Der zweite Operand. der Wert, der dem ersten Operanden hinzugefügt werden soll.

## <a name="return-value"></a>Rückgabewert

Der Wert des zweiten Operanden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `_InterlockedAddLargeStatistic` systeminterne Funktion ist nicht atomarisch, weil Sie als zwei separate, gesperrte Anweisungen implementiert ist. Ein atomarischer 64-Bit-Lesevorgang, der während der Ausführung des systeminternen Threads in einem anderen Thread auftritt, kann zu einem Lesevorgang eines inkonsistenten Werts führen.

`_InterlockedAddLargeStatistic`verhält sich als Barriere mit Lese-/Schreibzugriff. Weitere Informationen finden Sie unter [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
