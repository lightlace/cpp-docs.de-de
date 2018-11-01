---
title: Compilerwarnung (Stufe 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: 833546d20454e6104a2d5fcb272bf5bb9518ea44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460943"
---
# <a name="compiler-warning-level-3-c4738"></a>Compilerwarnung (Stufe 3) C4738

Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust

C4738 gibt eine Warnung aus, dass das Ergebnis einer Zuweisung, umgewandelt, als Argument übergeben oder anderen Vorgang möglicherweise gerundet werden soll, oder dass der Vorgang nicht mehr Register genügend und Verwendung von Speicher (Überlauf) erforderlich sind. Dies kann zu Leistungseinbußen führen.

Um diese Warnung beheben, und vermeiden Sie runden, kompilieren Sie mit [fast](../../build/reference/fp-specify-floating-point-behavior.md) oder `double` anstelle von `float`.

Um diese Warnung beheben, und Vermeiden von Registern zur Neige geht, die Reihenfolge der Berechnungen ändern, und ändern Sie die Verwendung von Inlinefunktionen

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4738 generiert:

```
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```