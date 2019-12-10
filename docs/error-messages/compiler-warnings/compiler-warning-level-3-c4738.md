---
title: Compilerwarnung (Stufe 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: c1989518c3965f8faa54a05b2925d0e37455625e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991706"
---
# <a name="compiler-warning-level-3-c4738"></a>Compilerwarnung (Stufe 3) C4738

Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust

C4738 warnt, dass das Ergebnis einer Zuweisung, eines Umwandlungs Vorgangs, eines übergebenen Arguments oder eines anderen Vorgangs möglicherweise gerundet werden muss oder dass der Vorgang nicht aus Registern besteht und für die Verwendung des Arbeitsspeichers (Überlauf) benötigt wird. Dies kann zu Leistungseinbußen führen.

Kompilieren Sie mit [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md) , oder verwenden Sie `double` anstelle von `float`, um diese Warnung zu beheben und eine Rundung zu vermeiden.

Ändern Sie die Reihenfolge der Berechnung, und ändern Sie die Verwendung von Inlining, um diese Warnung zu beheben und das Ausführen von Registern zu vermeiden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4738 generiert:

```cpp
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
