---
title: 2.6.3 Barrier-Direktive | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8654534143e6feed06e93406c8fe03983ee9c2fc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429148"
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