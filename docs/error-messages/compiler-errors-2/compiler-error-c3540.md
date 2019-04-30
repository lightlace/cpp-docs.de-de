---
title: Compilerfehler C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 57e4145557272f76a890a356c79982346cd74d7e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345482"
---
# <a name="compiler-error-c3540"></a>Compilerfehler C3540

"Type": "sizeof" kann nicht angewendet werden, um ein Typ, der "auto" enthält

Die ["sizeof"](../../cpp/sizeof-operator.md) Operator kann nicht in den angegebenen Typ angewendet werden, da er enthält die `auto` Spezifizierer.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3540 ergeben.

```
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