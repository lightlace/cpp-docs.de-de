---
title: __Func__ | Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __func__
dev_langs: C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ddb92e84545de175734550eca8911590fa1d539
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="func"></a>__Func__

**(C ++ 11)**  Der vordefinierte Bezeichner &#95; &#95; Func #95; &#95; wird als eine Zeichenfolge, die den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion enthält implizit definiert. &#95; &#95; Func &#95; &#95; wird vom C++-Standard vorgegeben und ist keine Microsoft-Erweiterung.

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