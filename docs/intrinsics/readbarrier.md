---
title: _ReadBarrier
ms.date: 11/04/2016
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: d898f85398fffa79a9b484f0f82343b1675b61e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565164"
---
# <a name="readbarrier"></a>_ReadBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
>  Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:: Atomic\<T >](../standard-library/atomic.md) , definiert sind, der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Verwenden Sie für den Hardwarezugriff die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption zusammen mit den [flüchtige](../cpp/volatile-cpp.md) Schlüsselwort.

## <a name="syntax"></a>Syntax

```
void _ReadBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die systeminterne `_ReadBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)