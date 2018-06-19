---
title: __Func__ | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78a249fe5b111c17c29895edcdc3fa5ba2f27a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413593"
---
# <a name="func"></a>__func__

**(C ++ 11)**  Der vordefinierte Bezeichner &#95; &#95;Func&#95; &#95; ist implizit als eine Zeichenfolge, die den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion enthält definiert. &#95;&#95;Func&#95; &#95; wird vom C++-Standard vorgegeben und ist keine Microsoft-Erweiterung.

## <a name="syntax"></a>Syntax

```cpp
__func__
```

## <a name="return-value"></a>Rückgabewert

Gibt eine Null-terminierte const Char ein Array von Zeichen, das den Namen der Funktion enthält.

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