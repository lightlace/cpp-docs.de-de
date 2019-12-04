---
title: Compilerfehler C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: f5799511575617ad1705bbce50a939ee46599628
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755342"
---
# <a name="compiler-error-c3285"></a>Compilerfehler C3285

Die For Each-Anweisung kann nicht bei Variablen vom Typ "Typ" verwendet werden.

Mit der `for each` -Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt.

Weitere Informationen finden Sie unter [for each, in](../../dotnet/for-each-in.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3285 generiert.

```cpp
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```
