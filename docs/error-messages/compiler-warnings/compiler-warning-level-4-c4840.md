---
title: Compilerwarnung (Stufe 4) C4840 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2018
ms.topic: error-reference
f1_keywords:
- C4840
dev_langs:
- C++
helpviewer_keywords:
- C4840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0baf70ac7fd4d07958478d2eef455c7dc395e221
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601825"
---
# <a name="compiler-warning-level-4-c4840"></a>Compilerwarnung (Stufe 4) C4840

> nicht Portable Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion
  
## <a name="remarks"></a>Hinweise

Klassen oder Strukturen, die an eine Variadic-Funktion übergeben werden müssen einfach kopierbar sein. Wenn solche Objekte übergeben werden, macht der Compiler einfach eine bitweise Kopie und ruft keinen Konstruktor oder Destruktor auf.

Diese Warnung ist ab, die in Visual Studio 2017 verfügbar.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4840 generiert, und es wird gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

Für Zeichenfolgen mit erstellte und verwaltete `CStringW`, bereitgestellten `operator LPCWSTR()` sollte verwendet werden, um die Umwandlung einer `CStringW` Objekt, das den Zeichenfolgenzeiger im C-Stil für von der Formatzeichenfolge erwartet wird:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```