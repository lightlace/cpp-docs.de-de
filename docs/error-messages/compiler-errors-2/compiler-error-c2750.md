---
title: Compilerfehler C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 56f4e6e1d6c392fc377fe5fdf11643ae8a2e503a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759606"
---
# <a name="compiler-error-c2750"></a>Compilerfehler C2750

"Typ": "New" kann nicht für den Verweistyp verwendet werden. Verwenden Sie stattdessen "gcnew".

Um eine Instanz eines CLR-Typs zu erstellen, die bewirkt, dass die Instanz auf dem Heap der Garbage Collection abgelegt wird, müssen Sie [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md)verwenden.

Im folgenden Beispiel wird C2750 generiert:

```cpp
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```
