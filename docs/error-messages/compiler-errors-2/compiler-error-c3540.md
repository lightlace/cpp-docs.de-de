---
title: Compilerfehler C3540 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3540
dev_langs:
- C++
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6525812d56a82ce2f5d8cad7a63250c726ce5193
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103270"
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