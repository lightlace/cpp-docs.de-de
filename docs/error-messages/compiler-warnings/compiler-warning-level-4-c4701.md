---
title: Compilerwarnung (Stufe 4) C4701
ms.date: 11/04/2016
f1_keywords:
- C4701
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
ms.openlocfilehash: 7d9b0041428af62c4b9d7a9a170547ab75222e94
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278423"
---
# <a name="compiler-warning-level-4-c4701"></a>Compilerwarnung (Stufe 4) C4701

möglicherweise nicht initialisierte lokale Variable "Name" verwendet

Die lokale Variable *Namen* kann verwendet werden können, ohne einen Wert zugewiesen wird. Dies kann zu unvorhersehbaren Ergebnissen führen.

## <a name="example"></a>Beispiel

Der folgende Code generiert C4701 und C4703.

```cpp
#include <malloc.h>

void func(int size)
{
    void* p;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr) // C4701 and C4703
        free(p);
}

void main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

Um diese Warnung zu beheben, initialisieren Sie die Variable, wie im folgenden Beispiel gezeigt:

```cpp
#include <malloc.h>

void func(int size)
{
    void* p = nullptr;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr)
        free(p);
}

void main()
{
    func(9);
}
```

## <a name="see-also"></a>Siehe auch

[Compilerwarnung (Ebene 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[Warnungen, / SDL und Verbessern der Erkennung von nicht initialisierten Variablen](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)