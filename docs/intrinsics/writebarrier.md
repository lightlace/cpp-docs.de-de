---
title: _WriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: b1b5ba2d70a8fc64eb47b3c6f3ff157214dcb94d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653023"
---
# <a name="writebarrier"></a>_WriteBarrier

**Microsoft-spezifisch**

Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.

> [!CAUTION]
>  Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:: Atomic\<T >](../standard-library/atomic.md), die definiert werden, der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Verwenden Sie für den Hardwarezugriff die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption zusammen mit den [flüchtige](../cpp/volatile-cpp.md) Schlüsselwort.

## <a name="syntax"></a>Syntax

```
void _WriteBarrier(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die systeminterne `_WriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)