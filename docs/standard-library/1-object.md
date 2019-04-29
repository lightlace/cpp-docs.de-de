---
title: _1-Objekt
ms.date: 11/04/2016
f1_keywords:
- _1
- std::_1
- functional/std::_1
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: 183df5c2ff039ff9438b1a00c63318e16dc84c37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411278"
---
# <a name="1-object"></a>_1-Objekt

Platzhalter für austauschbare Argumente.

## <a name="syntax"></a>Syntax

```cpp
namespace placeholders {
    extern unspecified _1,
    _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>Hinweise

Die Objekte `_1, _2, ... _M` sind Platzhalter festlegen, das das erste, zweite,..., n-te Argument in einem Funktionsaufruf in ein Objekt, das von zurückgegebene [binden](../standard-library/functional-functions.md#bind). Sie verwenden `_N`, um anzugeben, wo das n-te Argument bei Auswertung des Bindungsausdrucks eingefügt werden soll.

In dieser Implementierung lautet der Wert von `M` 20.

## <a name="example"></a>Beispiel

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[bind](../standard-library/functional-functions.md#bind)<br/>
[is_placeholder-Klasse](../standard-library/is-placeholder-class.md)<br/>
