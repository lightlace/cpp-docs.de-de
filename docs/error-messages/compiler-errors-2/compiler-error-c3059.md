---
title: Compilerfehler C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: 897ed2beb7634cec787f0776616d9a60596a979f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756460"
---
# <a name="compiler-error-c3059"></a>Compilerfehler C3059

"Var": Ein threadprivate-Symbol kann nicht in der <Klausel>-Klausel verwendet werden.

Ein [threadprivate](../../parallel/openmp/reference/threadprivate.md) Symbol wurde in einer Klausel verwendet.

Im folgenden Beispiel wird C3059 generiert.

```cpp
// C3059.cpp
// compile with: /openmp
#include "omp.h"
int x, y;
#pragma omp threadprivate(x, y)

int main() {
   #pragma omp parallel private(x, y)   // C3059
   {
      x = y;
   }
}
```

Mögliche Lösung:

```cpp
// C3059b.cpp
// compile with: /openmp
#include "omp.h"
int x = 0, y = 0;

int main() {
   #pragma omp parallel firstprivate(y) private(x)
   {
      x = y;
   }
}
```
