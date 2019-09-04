---
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 8bbcecf95daeef6ea2d40877d37e0eb6b7f3a0e8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217097"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
> Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:\<: Atomic T >](../standard-library/atomic.md) , die in der [ C++ Standard Bibliothek](../standard-library/cpp-standard-library-reference.md)definiert sind. Verwenden Sie für den Hardware Zugriff die [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption in Verbindung mit dem [volatile](../cpp/volatile-cpp.md) -Schlüsselwort.

## <a name="syntax"></a>Syntax

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die systeminterne `_ReadBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
