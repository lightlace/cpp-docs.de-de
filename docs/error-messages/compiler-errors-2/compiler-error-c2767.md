---
title: Compilerfehler C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 259e8a58abfa2dc5eacaa6c9f6e3d47b852f5c1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759814"
---
# <a name="compiler-error-c2767"></a>Compilerfehler C2767

nicht übereinstimmende oder winrtarray-Dimension: erwartete N Argument (e)-M angegeben

Die Deklaration eines verwalteten oder WinRT-Arrays wurde nicht ordnungsgemäß formatiert. Weitere Informationen finden Sie unter [Array](../../extensions/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C2767 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```
