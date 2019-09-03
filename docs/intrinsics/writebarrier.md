---
title: _WriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: a41f4c6c5cdd6b72e76a596622912e88fbd03f34
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219314"
---
# <a name="_writebarrier"></a>_WriteBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
> Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:\<: Atomic T >](../standard-library/atomic.md), die in der [ C++ Standard Bibliothek](../standard-library/cpp-standard-library-reference.md)definiert sind. Verwenden Sie für den Hardware Zugriff die [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption in Verbindung mit dem [volatile](../cpp/volatile-cpp.md) -Schlüsselwort.

## <a name="syntax"></a>Syntax

```C
void _WriteBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die systeminterne `_WriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
