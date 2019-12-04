---
title: Compilerfehler C3024
ms.date: 11/04/2016
f1_keywords:
- C3024
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
ms.openlocfilehash: e344fe5eeffb32b3490b41a3d3374638cc19ba1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742014"
---
# <a name="compiler-error-c3024"></a>Compilerfehler C3024

schedule(runtime): Der chunk_size -Ausdruck ist nicht zulässig.

An den Laufzeitparameter der schedule-Klausel kann kein Wert übergeben werden.

Im folgenden Beispiel wird C3024 generiert:

```cpp
// C3024.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main() {
   int i;

   #pragma omp parallel for schedule(runtime, 10)   // C3024
   for (i = 0; i < 10; ++i) ;

   #pragma omp parallel for schedule(runtime)   // OK
   for (i = 0; i < 10; ++i) ;
}
```
