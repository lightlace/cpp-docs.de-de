---
title: Compilerfehler C3698
ms.date: 11/04/2016
f1_keywords:
- C3698
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
ms.openlocfilehash: 29c1df618d6a8a14f441c09a6db0f9457133910b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758046"
---
# <a name="compiler-error-c3698"></a>Compilerfehler C3698

"Typ": dieser Typ kann nicht als Argument von "Operator" verwendet werden.

Ein verwaltetes Objekt wurde falsch deklariert.

Im folgenden Beispiel wird C3698 generiert:

```cpp
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```
