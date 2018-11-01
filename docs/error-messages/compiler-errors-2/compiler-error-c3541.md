---
title: Compilerfehler C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 356936ee09b75b6930840e015d00ccebb2fd8bc2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596377"
---
# <a name="compiler-error-c3541"></a>Compilerfehler C3541

"Type": Typeid kann nicht angewendet werden, um ein Typ, der "auto" enthält

Die [Typeid](../../windows/typeid-cpp-component-extensions.md) Operator kann nicht in den angegebenen Typ angewendet werden, da er enthält die `auto` Spezifizierer.

## <a name="example"></a>Beispiel

Im folgende Beispiel ergibt C3541.

```
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
[typeid](../../windows/typeid-cpp-component-extensions.md)