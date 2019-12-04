---
title: Compilerfehler C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 94f35f9f3bf64e09087f28a11a4fb9802d9d3c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761516"
---
# <a name="compiler-error-c3540"></a>Compilerfehler C3540

"Type": "sizeof" kann nicht auf einen Typ angewendet werden, der "Auto" enthält.

Der [sizeof](../../cpp/sizeof-operator.md) -Operator kann nicht auf den angezeigtem Typ angewendet werden, weil er den `auto` Spezifizierer enthält.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3540 erzeugt.

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof-Operator](../../cpp/sizeof-operator.md)
