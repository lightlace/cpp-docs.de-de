---
title: Compilerfehler C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 344fd32e66881c2529ddb1f9185c25752f0a736c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754978"
---
# <a name="compiler-error-c3039"></a>Compilerfehler C3039

"var": Die Indexvariable in der For-Anweisung von OpenMP kann keine reduction-Variable sein.

Da eine Indexvariable implizit privat ist, kann die Variable nicht in einer [reduction](../../parallel/openmp/reference/reduction.md) -Klausel in der einschließenden [parallel](../../parallel/openmp/reference/parallel.md) -Direktive verwendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3039 generiert:

```cpp
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
