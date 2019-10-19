---
title: Variadic-Makros
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: de4d3a7f03f613cb058e564664f01837df23aefb
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587885"
---
# <a name="variadic-macros"></a>Variadic-Makros

Variadic-Makros sind funktionsähnliche Makros, die eine variable Anzahl von Argumenten enthalten.

## <a name="remarks"></a>Hinweise

Um Variadic-Makros verwenden zu können, können die Auslassungs Zeichen als endgültiges formales Argument in einer Makro Definition angegeben werden, und der Ersetzungs Bezeichner `__VA_ARGS__` kann in der Definition verwendet werden, um die zusätzlichen Argumente einzufügen.  `__VA_ARGS__` wird durch alle Argumente ersetzt, die mit den Auslassungs Zeichen (einschließlich Kommas) identisch sind.

Der C-Standard gibt an, dass mindestens ein Argument an die Auslassungs Zeichen übermittelt werden muss, um sicherzustellen, dass das Makro nicht in einen Ausdruck mit einem nachfolgenden Komma aufgelöst wird. Die herkömmliche Microsoft C++ -Implementierung unterdrückt ein nach gestelltes Komma, wenn keine Argumente an die Auslassungs Zeichen übermittelt werden. Wenn die `/experimental:preprocessor`-Compileroption festgelegt ist, wird das nachfolgende Komma nicht unterdrückt.

## <a name="example"></a>Beispiel

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>Siehe auch

[Makros (C/C++)](../preprocessor/macros-c-cpp.md)
