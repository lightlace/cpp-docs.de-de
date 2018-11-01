---
title: Compilerfehler C3056
ms.date: 11/04/2016
f1_keywords:
- C3056
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
ms.openlocfilehash: d33aa6679c6dc68b7f1a62e75aff6fadc65dc7bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447410"
---
# <a name="compiler-error-c3056"></a>Compilerfehler C3056

'symbol': Das Symbol befindet sich nicht im gleichen Bereich wie die 'threadprivate'-Direktive.

Ein in einer [threadprivate](../../parallel/openmp/reference/threadprivate.md) -Klausel verwendetes Symbol muss sich im gleichen Bereich wie die `threadprivate` -Klausel befinden.

Im folgenden Beispiel wird C3056 generiert:

```
// C3056.cpp
// compile with: /openmp
int x, y;
void test() {
   #pragma omp threadprivate(x, y)   // C3056
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Mögliche Lösung:

```
// C3056b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)
void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```