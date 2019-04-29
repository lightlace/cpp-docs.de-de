---
title: Compilerfehler C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 69be1b25254119108e517cee2f1e14368e0163f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350100"
---
# <a name="compiler-error-c3039"></a>Compilerfehler C3039

"var": Die Indexvariable in der For-Anweisung von OpenMP kann keine reduction-Variable sein.

Da eine Indexvariable implizit privat ist, kann die Variable nicht in einer [reduction](../../parallel/openmp/reference/reduction.md) -Klausel in der einschließenden [parallel](../../parallel/openmp/reference/parallel.md) -Direktive verwendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3039 generiert:

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```