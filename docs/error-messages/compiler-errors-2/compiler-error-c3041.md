---
title: Compilerfehler C3041
ms.date: 11/04/2016
f1_keywords:
- C3041
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
ms.openlocfilehash: 43f75e9d054f574eb121d20eb35d302cef849566
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479130"
---
# <a name="compiler-error-c3041"></a>Compilerfehler C3041

"var": Die Variable in der copyprivate-Klausel muss im umschließenden Kontext privat sein

Eine an [copyprivate](../../parallel/openmp/reference/copyprivate.md) übergebene Variable kann im umschließenden Kontext nicht freigegeben werden.

Im folgenden Beispiel wird C3041 generiert.

```
// C3041.cpp
// compile with: /openmp /c
#include "omp.h"
double d;
int main() {
   #pragma omp parallel shared(d)
   // try the following line instead
   // #pragma omp parallel private(d)
   {
      // or don't make d copyprivate
      #pragma omp single copyprivate(d)   // C3041
      {
      }
   }
}
```