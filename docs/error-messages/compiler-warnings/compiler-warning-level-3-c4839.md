---
title: Compilerwarnung (Stufe 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 09b6e5b8dc984b35df7de96f5cf8610f2b0f16af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401526"
---
# <a name="compiler-warning-level-3-c4839"></a>Compilerwarnung (Stufe 3) C4839

> nicht standardmäßige Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion

Klassen oder Strukturen, die an eine Variadic-Funktion, z. B. übergeben werden `printf` muss einfach kopierbar sein. Wenn solche Objekte übergeben werden, macht der Compiler einfach eine bitweise Kopie und ruft keinen Konstruktor oder Destruktor auf.

Diese Warnung ist ab, die in Visual Studio 2017 verfügbar.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4839 generiert:

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function
}
```

Sie können eine Memberfunktion aufrufen, die einen einfachen kopierbaren Typ zurückgibt, um den Fehler zu beheben,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Für Zeichenfolgen mit erstellte und verwaltete `CStringW`, bereitgestellten `operator LPCWSTR()` sollte verwendet werden, um die Umwandlung einer `CStringW` Objekt an den C-Zeiger, die von der Formatzeichenfolge erwartet wird.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```