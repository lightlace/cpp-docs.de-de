---
title: Compilerfehler C3033
ms.date: 11/04/2016
f1_keywords:
- C3033
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
ms.openlocfilehash: 57c2cc120a5c155d02e0e601dc2ff8924badbe67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460893"
---
# <a name="compiler-error-c3033"></a>Compilerfehler C3033

"Var": Die Variable in der Klausel-Klausel kann keinen konstant qualifizierten Typ aufweisen.

Werte, die an bestimmte Klauseln übergeben werden, dürfen keine `const` -Variablen sein.

Im folgenden Beispiel wird C3033 generiert:

```
// C3033.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   const int val = 1;
   int val2 = 1;

   #pragma omp parallel reduction(+ : val)   // C3033
   ;

   #pragma omp parallel reduction(+ : val2)   // OK
   ;
}
```