---
title: Compilerfehler C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: 88c0c9747f98c6850f3e9b4341bdcdef915ac754
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761350"
---
# <a name="compiler-error-c3045"></a>Compilerfehler C3045

Es wurde erwartet, dass auf die sections-Direktive von OpenMP eine Verbundanweisung folgt. '{' fehlt

Ein durch geschweifte Klammern begrenzter Codeblock muss auf eine [sections](../../parallel/openmp/reference/sections-openmp.md) -Direktive folgen.

Im folgenden Beispiel wird C3045 generiert:

```cpp
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```
