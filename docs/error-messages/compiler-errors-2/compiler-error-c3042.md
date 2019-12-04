---
title: Compilerfehler C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: 4347e5ee0e61ada700082b4954b616ce894e57b9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761389"
---
# <a name="compiler-error-c3042"></a>Compilerfehler C3042

copyprivate- und nowait-Klauseln dürfen nicht zusammen in der 'Direktive'-Direktive von OpenMP vorkommen.

Die [copyprivate](../../parallel/openmp/reference/copyprivate.md) - und [nowait](../../parallel/openmp/reference/nowait.md) -Klauseln schließen sich in der angegebenen Richtung gegenseitig aus. Entfernen Sie eine oder beide der `copyprivate` - oder `nowait` -Klauseln.

Im folgenden Beispiel wird C3042 generiert.

```cpp
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```
