---
title: Compilerfehler C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537551"
---
# <a name="compiler-error-c3003"></a>Compilerfehler C3003

'Direktive': Nach Direktivenklauseln ist kein OpenMP-Direktivenname zulässig.

Ein OpenMP-Direktivenname darf nicht auf eine OpenMP-Direktivenklausel folgen.

Im folgenden Beispiel wird C3003 generiert:

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```