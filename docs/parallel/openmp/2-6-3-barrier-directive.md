---
title: 2.6.3 barrier-Anweisung
ms.date: 11/04/2016
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
ms.openlocfilehash: 9079dce4b2a27e91e349fd0df8414d38cd245d2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637020"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier-Anweisung

Die **Barriere** Richtlinie synchronisiert alle Threads in einem Team. Wenn gefunden, wartet jeden Thread im Team, das, bis alle anderen dieser Punkt erreicht haben. Die Syntax der **Barriere** Richtlinie lautet wie folgt:

```
#pragma omp barrier new-line
```

Nachdem alle Threads in das Team die Barriere aufgetreten ist, beginnt jeder Thread im Team, das die Anweisungen nach der Barrier-Direktive parallel ausgeführt. Beachten Sie, dass die **Barriere** Richtlinie verfügt nicht über eine C-Language-Anweisung als Teil der Syntax, es gibt einige Einschränkungen für die Platzierung innerhalb eines Programms. Finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik. Das folgende Beispiel veranschaulicht diese Einschränkungen.

```
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```