---
title: Compilerwarnung (Stufe 4) C4701
ms.date: 11/04/2016
f1_keywords:
- C4701
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
ms.openlocfilehash: b83ad810da06de1f9d640477f73d4393c932054a
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518386"
---
# <a name="compiler-warning-level-4-c4701"></a>Compilerwarnung (Stufe 4) C4701

Möglicherweise wurde die nicht initialisierte lokale Variable "Name" verwendet.

Der *Name* der lokalen Variablen wurde möglicherweise ohne Zuweisung eines Werts verwendet. Dies kann zu unvorhersehbaren Ergebnissen führen.

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

int main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

Um diese Warnung zu korrigieren, initialisieren Sie die Variable wie im folgenden Beispiel gezeigt:

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

int main()
{
    func(9);
}
```

## <a name="see-also"></a>Siehe auch

[Compilerwarnung (Ebene 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[Warnungen,/SDL und verbessern der Erkennung nicht initialisierter Variablen](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)
