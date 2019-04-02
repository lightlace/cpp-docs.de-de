---
title: Compilerfehler C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: c56be16504dbdad0c441ad90182fa99ef0445dcf
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772630"
---
# <a name="compiler-error-c3541"></a>Compilerfehler C3541

"Type": Typeid kann nicht angewendet werden, um ein Typ, der "auto" enthält

Die [Typeid](../../extensions/typeid-cpp-component-extensions.md) Operator kann nicht in den angegebenen Typ angewendet werden, da er enthält die `auto` Spezifizierer.

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
[typeid](../../extensions/typeid-cpp-component-extensions.md)