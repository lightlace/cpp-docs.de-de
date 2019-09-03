---
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: d755d045970da01d2eee33377c1452191eac4fe2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217982"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
> Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:\<: Atomic T >](../standard-library/atomic.md), die in der [ C++ Standard Bibliothek](../standard-library/cpp-standard-library-reference.md)definiert sind. Verwenden Sie für den Hardware Zugriff die [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption in Verbindung mit dem [volatile](../cpp/volatile-cpp.md) -Schlüsselwort.

## <a name="syntax"></a>Syntax

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die systeminterne `_ReadWriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_WriteBarrier](../intrinsics/writebarrier.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
