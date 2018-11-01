---
title: Compilerfehler C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: d0a5da87feeabc5d3d5b558ce0dd6bdfe3869d53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595103"
---
# <a name="compiler-error-c3034"></a>Compilerfehler C3034

Die OpenMP directive1-Direktive von kann nicht direkt in der directive1-Direktive geschachtelt werden.

Bestimmte Direktiven können nicht geschachtelt werden. Um diesen Fehler zu beheben, können Sie die Anweisungen der beiden Direktiven in den Block einer Direktive zusammenführen, oder Sie können aufeinander folgende Direktiven erstellen.

Im folgenden Beispiel wird C3034 generiert:

```
// C3034.cpp
// compile with: /openmp /link vcomps.lib
int main() {

   #pragma omp single
   {
      #pragma omp single   // C3034
      {
      ;
      }
   }

   // Two consecutive single clauses are OK.
   #pragma omp single
   {
   }

   #pragma omp single
   {
   }
}
```