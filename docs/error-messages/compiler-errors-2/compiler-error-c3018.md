---
title: Compilerfehler C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 7a16c81cf2b9c2a815d2e35d10ae82d5a75547b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386719"
---
# <a name="compiler-error-c3018"></a>Compilerfehler C3018

"var1": OpenMP 'for' Test oder das Inkrement muss Index Indexvariable "var2" verwenden.

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