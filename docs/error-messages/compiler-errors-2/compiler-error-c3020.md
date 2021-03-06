---
title: Compilerfehler C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: b066e813203f10b902e49a62af97a9a041874752
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742118"
---
# <a name="compiler-error-c3020"></a>Compilerfehler C3020

"var": die Index Variable der for-Schleife von OpenMP kann im Schleifen Text nicht geändert werden.

Eine OpenMP-`for` Schleife kann den Index (Schleifen Indikator) nicht im Text der `for` Schleife ändern.

Im folgenden Beispiel wird C3020 generiert:

```cpp
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

Eine mit [Last private](../../parallel/openmp/reference/lastprivate.md) deklarierte Variable kann nicht als Index innerhalb einer parallelisierten Schleife verwendet werden.

Im folgenden Beispiel wird C3020 für den zweiten Last private-Wert verwendet, da Last private einen Schreibvorgang idx_a in der äußersten for-Schleife auslöst. Der erste Last private-Fehler gibt keinen Fehler aus, da Last private einen Schreibvorgang in idx_a außerhalb der äußersten for-Schleife auslöst (technisch gesehen am Ende der letzten Iterationen). Im folgenden Beispiel wird C3020 generiert.

```cpp
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```cpp
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```
