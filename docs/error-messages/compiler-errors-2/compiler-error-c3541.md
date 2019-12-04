---
title: Compilerfehler C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 1308ff91bcebabc5495b015321494f3457cf2d1e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761503"
---
# <a name="compiler-error-c3541"></a>Compilerfehler C3541

"Typ": typeid kann nicht auf einen Typ angewendet werden, der "Auto" enthält.

Der [typeid](../../extensions/typeid-cpp-component-extensions.md) -Operator kann nicht auf den angezeigtem Typ angewendet werden, weil er den `auto` Spezifizierer enthält.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3541 erzeugt.

```cpp
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
