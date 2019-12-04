---
title: Compilerfehler C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 4eb50ddac51ea78ab3a28d7703384f02eb026ecb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743925"
---
# <a name="compiler-error-c2462"></a>Compilerfehler C2462

' Identifier ': ein Typ kann nicht in ' New-Expression ' definiert werden.

Sie können im Operand-Feld des `new` Operators keinen Typ definieren. Legen Sie die Typdefinition in einer separaten Anweisung ab.

Im folgenden Beispiel wird C2462 generiert:

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
