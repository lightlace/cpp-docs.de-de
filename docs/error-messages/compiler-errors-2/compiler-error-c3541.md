---
title: Compilerfehler C3541 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3541
dev_langs:
- C++
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0f9cb18089bcf8ce1688cabb261f91f868da247
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021719"
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