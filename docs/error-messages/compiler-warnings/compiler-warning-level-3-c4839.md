---
title: Compilerwarnung (Stufe 3) C4839 | Microsoft Docs
ms.date: 10/25/2017
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
ms.openlocfilehash: b72289eef03c56356865b0b62a999c417da570a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291956"
---
# <a name="compiler-warning-level-4-c4839"></a>Compilerwarnung (Stufe 4) C4839

> nicht standardmäßige Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion

In Visual Studio 2017 Klassen oder Strukturen, die an einer Variadic übergeben werden, funktionieren wie z. B. `printf` belanglos kopierbare werden muss. Wenn solche Objekte übergeben werden, macht der Compiler einfach eine bitweise Kopie und ruft keinen Konstruktor oder Destruktor auf.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4839 generiert:

```cpp
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

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Sie können eine Memberfunktion aufrufen, die einen einfachen kopierbaren Typ zurückgibt, um den Fehler zu beheben,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

oder Sie führen eine statische Umwandlung aus, um das Objekt zu konvertieren, bevor es übergeben wird:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Für Zeichenfolgen erstellt und verwaltet mithilfe `CStringW`, bereitgestellten `operator LPCWSTR()` sollte verwendet werden, um die Umwandlung einer `CStringW` Objekt in der C-Zeiger erwartet wird die Formatzeichenfolge.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```