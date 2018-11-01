---
title: A. 16   Verwenden von Sperren
ms.date: 11/04/2016
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
ms.openlocfilehash: 6afb94660acdc79ea5a7eb61d3bf7e21fd70d751
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458981"
---
# <a name="a16---using-locks"></a>A. 16   Verwenden von Sperren

Im folgenden Beispiel (für [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41) Beachten Sie, dass das Argument für die Lock-Funktionen geben muss `omp_lock_t`, und dass keine Notwendigkeit besteht, sie zu leeren.  Die Lock-Funktionen dazu führen, dass die Threads im Leerlauf ist beim Warten auf einen Eintrag in den ersten kritischen Abschnitt, aber eine andere Aktion beim Warten auf einen Eintrag in der zweiten ausführen.  Die `omp_set_lock` Funktion-Blöcken, aber die `omp_test_lock` Funktion jedoch nicht, ermöglichen, dass die Arbeit in Skip()"durchgeführt werden.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```