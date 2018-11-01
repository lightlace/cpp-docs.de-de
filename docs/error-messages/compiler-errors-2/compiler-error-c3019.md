---
title: Compilerfehler C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: bba90917614cbc8facb182659c288f9823d8ab45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432551"
---
# <a name="compiler-error-c3019"></a>Compilerfehler C3019

Das Inkrement in OpenMP der for-Anweisung weist eine ungültige form

Das Inkrement Teil einem OpenMP `for` -Schleife muss die Indexvariable sowohl auf der linken und rechten Seite des Operators verwenden.

Im folgende Beispiel wird die C3019 generiert:

```
// C3019.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 1, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i = j + n)   // C3019
      // Try the following line instead:
      // for (i = 0; i < 10; i++)
         j *= 2;
   }
}
```