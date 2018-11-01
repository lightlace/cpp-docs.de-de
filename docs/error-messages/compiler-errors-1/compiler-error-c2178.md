---
title: Compilerfehler C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: cd153bb5b331872bfe35b046d41612998bd0eff7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622559"
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
