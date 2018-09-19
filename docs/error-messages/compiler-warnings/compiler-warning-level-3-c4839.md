---
title: Compilerwarnung (Stufe 3) C4839 | Microsoft-Dokumentation
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4839
dev_langs:
- C++
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14a79c6abb118fb173382be87ebda4316545c65a
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601404"
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