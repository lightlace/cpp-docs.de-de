---
title: Compilerfehler C3029
ms.date: 11/04/2016
f1_keywords:
- C3029
helpviewer_keywords:
- C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
ms.openlocfilehash: a003a0b8fcba3609c355ae467a11b4024a0529d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385809"
---
# <a name="compiler-error-c3029"></a>Compilerfehler C3029

"Symbol": Kann nur einmal in Datenfreigabeklauseln in einer OpenMP-Direktive vorkommen.

Ein Symbol wurde in mindestens einer Klausel in einer Direktive mehr als einmal verwendet. Das Symbol kann in der Direktive nur einmal verwendet werden.

Im folgenden Beispiel wird C3029 generiert:

```
// C3029.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

int g_i;

int main() {
   int i, x;

   #pragma omp parallel reduction(+ : x, x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;

   #pragma omp parallel private(x) reduction(+ : x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;
}
```