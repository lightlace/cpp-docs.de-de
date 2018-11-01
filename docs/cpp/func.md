---
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: eecd3efea6239c92a8bc81c0ed13a9563e5b87d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438583"
---
# <a name="func"></a>__func__

**(C ++ 11)**  Der vordefinierte Bezeichner &#95; &#95;Func&#95; &#95; ist implizit als eine Zeichenfolge, die den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion enthält definiert. &#95;&#95;Func&#95; &#95; wird vom C++-Standard vorgegeben und keine Microsoft-Erweiterung.

## <a name="syntax"></a>Syntax

```cpp
__func__
```

## <a name="return-value"></a>Rückgabewert

Gibt eine Null-terminierte const Char-Array von Zeichen, das den Namen der Funktion enthält.

## <a name="example"></a>Beispiel

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>Anforderungen

C++11