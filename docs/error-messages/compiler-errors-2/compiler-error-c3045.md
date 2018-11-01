---
title: Compilerfehler C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: 9beae880d840f1cd1ac73f51ebeac8883882dd92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620817"
---
# <a name="compiler-error-c3045"></a>Compilerfehler C3045

Es wurde erwartet, dass auf die sections-Direktive von OpenMP eine Verbundanweisung folgt. '{' fehlt

Ein durch geschweifte Klammern begrenzter Codeblock muss auf eine [sections](../../parallel/openmp/reference/sections-openmp.md) -Direktive folgen.

Im folgenden Beispiel wird C3045 generiert:

```
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