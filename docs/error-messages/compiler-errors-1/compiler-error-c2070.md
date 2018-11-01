---
title: Compilerfehler C2070
ms.date: 11/04/2016
f1_keywords:
- C2070
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
ms.openlocfilehash: 221b42e6425c84f4e34c99872fc0e51716e2db1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581336"
---
# <a name="compiler-error-c2070"></a>Compilerfehler C2070

'Typ': Ungültiger Sizeof-Operand

Die ["sizeof"](../../cpp/sizeof-operator.md) Operator muss ein Ausdruck oder einen Typ an.

Im folgende Beispiel wird die C2070 generiert:

```
// C2070.cpp
void func() {}
int main() {
   int a;
   a = sizeof(func);   // C2070
}
```

Mögliche Lösung:

```
// C2070b.cpp
void func() {}
int main() {
   int a;
   a = sizeof(a);
}
```