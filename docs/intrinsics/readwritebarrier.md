---
title: _ReadWriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: a279017e57c8bf828b302940463bd0b3504f085d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626160"
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
>  Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:: Atomic\<T >](../standard-library/atomic.md), die definiert werden, der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Verwenden Sie für den Hardwarezugriff die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption zusammen mit den [flüchtige](../cpp/volatile-cpp.md) Schlüsselwort.

## <a name="syntax"></a>Syntax

```
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die systeminterne `_ReadWriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_WriteBarrier](../intrinsics/writebarrier.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)