---
title: Compilerfehler C3029 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3029
dev_langs:
- C++
helpviewer_keywords:
- C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfeacd011f4df88820de6746707ec6b1300795c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108715"
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