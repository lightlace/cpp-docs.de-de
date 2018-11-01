---
title: alignof und alignas (C++)
ms.date: 11/04/2016
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
ms.openlocfilehash: e5d023d7969764bdd36030a508abdd94068e48b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493651"
---
# <a name="alignof-and-alignas-c"></a>alignof und alignas (C++)

Die **Alignas** Typspezifizierer ist eine portierbare, C++-Standardmethode, die eine benutzerdefinierte Ausrichtung von Variablen und benutzerdefinierte Typen anzugeben. Die **"alignof"** -Operator ist ebenfalls eine standardmäßige, portierbare Möglichkeit, die Ausrichtung eines angegebenen Typs oder einer Variablen zu erhalten.

## <a name="example"></a>Beispiel

Sie können **Alignas** auf eine Klasse union, oder auf einzelne Elemente. Wenn mehrere **Alignas** Spezifizierer gefunden, wählt der Compiler den strengsten davon aus (denjenigen mit dem größten Wert) wählen.

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>Siehe auch

[Ausrichtung](../cpp/alignment-cpp-declarations.md)