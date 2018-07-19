---
title: Constexpr Lambda-Ausdrücke in C++ | Microsoft Docs
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e01f41aaf8b761020f57625e7cbf06f8fba2659
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418899"
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