---
title: Variadic-Makros
ms.date: 11/04/2016
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: da159ef979ccc38845064debebae55356bc9e9bd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022839"
---
# <a name="variadic-macros"></a>Variadic-Makros

Variadic-Makros sind funktionsähnliche Makros, die eine variable Anzahl von Argumenten enthalten.

## <a name="remarks"></a>Hinweise

Um Variadic-Makros zu verwenden, kann das Auslassungszeichen als endgültiges formales Argument in einer Makrodefinition stehen und die Austausch-ID angegeben werden `__VA_ARGS__` kann in der Definition verwendet werden, um die zusätzlichen Argumente einfügen.  `__VA_ARGS__` wird von allen Argumenten ersetzt, die mit den Auslassungspunkten, einschließlich Kommas zwischen ihnen zu entsprechen.

Der C-Standard gibt an, dass mindestens ein Argument an die Auslassungszeichen übergeben werden muss, um sicherzustellen, dass das Makro sich nicht in einen Ausdruck mit einem nachfolgenden Komma auflöst.  Die Implementierung von Visual C++ unterdrückt ein nachfolgendes Komma, wenn keine Argumente an die Auslassungszeichen übergeben werden.

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