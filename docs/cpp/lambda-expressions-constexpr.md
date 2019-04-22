---
title: Constexpr-Lambdaausdrücke in C++
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: d1bc60a6da813e54c857da38b0164f544216be00
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59424182"
---
# <a name="constexpr-lambda-expressions-in-c"></a>Constexpr-Lambdaausdrücke in C++

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Ein Lambda-Ausdruck kann deklariert werden, als **"constexpr"** oder in einem konstanten Ausdruck verwendet werden, wenn die Initialisierung der einzelnen Datenmember, das erfasst oder führt in einem konstanten Ausdruck zulässig ist.

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

Ein Lambda-Ausdruck ist implizit **"constexpr"** Wenn das Ergebnis die Anforderungen erfüllt, eine **"constexpr"** Funktion:

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Wenn ein Lambda-Ausdruck implizit oder explizit ist **"constexpr"**, und Sie diese in einen Funktionszeiger konvertieren, die sich ergebende Funktion ist auch **"constexpr"**:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Funktionsobjekte in der C++-Standardbibliothek](../standard-library/function-objects-in-the-stl.md)<br/>
[Funktionsaufruf](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)