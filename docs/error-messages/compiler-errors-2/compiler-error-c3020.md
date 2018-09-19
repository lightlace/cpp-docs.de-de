---
title: Compilerfehler C3020 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3020
dev_langs:
- C++
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7f86d116c1a830db54490f3e5231d837d4246c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060641"
---
# <a name="compiler-error-c3020"></a>Compilerfehler C3020

"Var": Indexvariable der for-Schleife von OpenMP kann nicht im Schleifenkörper geändert werden

Eine OpenMP `for` -Schleife kann nicht geändert werden den Index (Schleifenzähler) im Hauptteil der `for` Schleife.

Im folgende Beispiel wird die C3020 generiert:

```
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

Eine Variable mit [Lastprivate](../../parallel/openmp/reference/lastprivate.md) kann nicht als Index in eine parallele Schleife verwendet werden.

Im folgende Beispiel wird für die zweite Lastprivate C3020 angezeigt, da dadurch, einen Schreibvorgang in den Idx_a innerhalb der äußersten for-Schleife ausgelöst wird. Der erste Lastprivate wird keine Fehlermeldung ausgegeben, da dadurch einen Schreibvorgang in Idx_a außerhalb der äußersten for-Schleife (technisch gesehen ist am Ende des letzten Durchlaufs) auslöst. Im folgende Beispiel wird die C3020 generiert.

```
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

```
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