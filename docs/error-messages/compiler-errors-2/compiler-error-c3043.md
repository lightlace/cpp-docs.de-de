---
title: Compilerfehler C3043
ms.date: 11/04/2016
f1_keywords:
- C3043
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
ms.openlocfilehash: 75ab43576a3b2135e174ba512ad8a46aa330f750
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604463"
---
# <a name="compiler-error-c3043"></a>Compilerfehler C3043

Die critical-Direktive von OpenMP kann nicht in einer critical-Direktive mit dem gleichen Namen geschachtelt werden.

Die [critical](../../parallel/openmp/reference/critical.md) -Direktive kann nicht in einer `critical` -Direktive mit dem gleichen Namen geschachtelt werden.

Im folgenden Beispiel wird C3043 generiert:

```
// C3043.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n1 = 1, n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp critical(MyTest)
      {
         ++n2;

         #pragma omp critical(MyTest)   // C3043
         // try the following line instead
         // #pragma omp critical(MyTest2)
         {
            ++n3;
         }
      }
   }
}
```