---
title: Compilerwarnung (Stufe 4) C4938
ms.date: 11/04/2016
f1_keywords:
- C4938
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
ms.openlocfilehash: da2725a398a99b5943e128038e75622115a9e34f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280203"
---
# <a name="compiler-warning-level-4-c4938"></a>Compilerwarnung (Stufe 4) C4938

"Var": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen

[/fp:strict](../../build/reference/fp-specify-floating-point-behavior.md) oder [fenv_access](../../preprocessor/fenv-access.md) sollte nicht mit reduction-Gleitkommavorgängen von OpenMP verwendet werden, da die Summe in einer anderen Reihenfolge berechnet wird. Daher können die Ergebnisse von den Ergebnissen ohne "/openmp" abweichen.

Im folgenden Beispiel wird C4938 generiert:

```
// C4938.cpp
// compile with: /openmp /W4 /fp:strict /c
// #pragma fenv_access(on)
extern double *a;

double test(int first, int last) {
   double sum = 0.0;
   #pragma omp parallel for reduction(+: sum)   // C4938
   for (int i = first ; i <= last ; ++i)
      sum += a[i];
   return sum;
}
```

Ohne explizite Parallelisierung wird die Summe wie folgt berechnet:

```
sum = a[first] + a[first + 1] + ... + a[last];
```

Mit expliziter Parallelisierung (und zwei Threads) wird die Summe wie folgt berechnet:

```
sum1 = a[first] + ... a[first + last / 2];
sum2 = a[(first + last / 2) + 1] + ... a[last];
sum = sum1 + sum2;
```