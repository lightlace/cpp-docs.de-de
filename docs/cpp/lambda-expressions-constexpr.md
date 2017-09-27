---
title: "Constexpr Lambda-Ausdrücke in C++ | Microsoft Docs"
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c6221118477c79d683d468469b1f87dfa33efded
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="constexpr-lambda-expressions-in-c"></a>Constexpr Lambda-Ausdrücke in C++
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): ein Lambda-Ausdruck kann als deklariert werden `constexpr` oder in einem Ausdruck Contant verwendet beim die Initialisierung der einzelnen Datenmember, It erfasst oder führt in einem konstanten Ausdruck zulässig ist.  

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
Ein Lambda-Ausdruck ist implizit `constexpr` das Ergebnis der Anforderungen erfüllt eine `constexpr` Funktion:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Wenn ein Lambda-Ausdruck implizit oder explizit ist `constexpr`, und Sie diese in einen Funktionszeiger konvertieren, ist die resultierende Funktion wird auch `constexpr`:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Function-Objekte in der C++-Standardbibliothek](../standard-library/function-objects-in-the-stl.md)   
 [Funktionsaufruf](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
