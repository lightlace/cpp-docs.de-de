---
title: A.31   Threadsichere Lock-Funktionen
ms.date: 11/04/2016
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
ms.openlocfilehash: ad0116dbb3491058e81fd271f4917f7eb7bff460
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613589"
---
# <a name="a31---thread-safe-lock-functions"></a>A.31   Threadsichere Lock-Funktionen

Das folgende C++-Beispiel veranschaulicht, wie ein Array von Sperren in einem parallelen Bereich zu initialisieren, indem Sie mithilfe von `omp_init_lock` ([Abschnitt 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) auf Seite 42).

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```