---
title: Compilerfehler C2540
ms.date: 11/04/2016
f1_keywords:
- C2540
helpviewer_keywords:
- C2540
ms.assetid: 92c805a3-2dd9-46ca-a63d-3845c18ecc95
ms.openlocfilehash: 1dc5dabee37955cb3f36830fe3c9e975e067be0b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758618"
---
# <a name="compiler-error-c2540"></a>Compilerfehler C2540

nicht konstanter Ausdruck als Array Grenze

Ein Array muss über eine Konstante Grenze verfügen.

Im folgenden Beispiel wird C2540 generiert:

```cpp
// C2540.cpp
void func(int n, int pC[]) {
   int i = ((int [n])pC)[1];   // C2540
}

void func2(int n, int pC[]) {
   int i = (pC)[1];   // OK
}

int main() {
   int pC[100];
   func(100, pC);
   func2(100, pC);
}
```
