---
title: Compilerfehler C2325
ms.date: 11/04/2016
f1_keywords:
- C2325
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
ms.openlocfilehash: 4ed0ca7403ff88ddcd0bd71123b1cbead7d020e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747812"
---
# <a name="compiler-error-c2325"></a>Compilerfehler C2325

' Typ ': Unerwarteter Typ rechts von ' Name '.

An einen Dekonstruktor mit einem falschen Typ wird ein-Befehl gerichtet.

Im folgenden Beispiel wird C2325 generiert:

```cpp
// C2325.cpp
// compile with: /c
class A {};
typedef A* pA_t;
void f() {
    A** ppa = new A *;
    ppa->~A*;   // C2325

   pA_t *ppa2 = new pA_t;
   ppa2->~pA_t();   // OK
}
```
