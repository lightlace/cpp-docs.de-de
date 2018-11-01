---
title: Constexpr-Lambdaausdrücke in C++
ms.date: 07/19/2017
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 937fae7da0f20e81ac5450d597af7a822219d654
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506599"
---
# <a name="constexpr-lambda-expressions-in-c"></a>Constexpr-Lambdaausdrücke in C++

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): kann ein Lambda-Ausdruck deklariert werden, als **"constexpr"** oder in einem Ausdruck Contant verwendet bei der die Initialisierung der einzelnen Data-Element, das sie erfasst oder führt ist in einem konstanten Ausdruck zulässig.

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