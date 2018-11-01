---
title: Compilerfehler C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 7a16c81cf2b9c2a815d2e35d10ae82d5a75547b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586965"
---
# <a name="compiler-error-c3018"></a>Compilerfehler C3018

"var1": Der Test oder das Inkrement in der For-Anweisung von OpenMP muss die Indexvariable "var2" verwenden.

Eine `for` -Schleife in einer OpenMP-Anweisung muss dieselbe Variable für ihren Test und ihr Inkrement wie für ihren Index verwenden.

Im folgenden Beispiel wird C3018 generiert:

```
// C3018.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 5;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; j < 10; ++i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; ++i)
         j *= 2;

      #pragma omp for
      for (i = 0; i < 10; j = j + i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; i = j + i)
         j *= 2;
   }
}
```