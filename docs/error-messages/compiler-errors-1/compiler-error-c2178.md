---
title: Compilerfehler C2178 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af9efdb3258e6793a17a26b552df8ba4e63c9107
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102334"
---
# <a name="compiler-error-c2178"></a>Compilerfehler C2178

"*Bezeichner*"kann nicht mit deklariert werden"*Spezifizierer*' Spezifizierer

Ein `mutable` Spezifizierer in einer Deklaration verwendet wurde, aber der Spezifizierer ist in diesem Kontext nicht zulässig.

Die `mutable` Spezifizierer kann nur auf Namen von klassendatenmembern angewendet werden, und kann nicht angewendet werden, um deklarierten Namen `const` oder `static`, und kann nicht auf Verweismember angewendet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie C2178 auftreten können und wie Sie diesen Fehler beheben.

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
