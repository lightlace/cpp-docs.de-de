---
title: A. 5 Verwenden der critical-Direktive | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99f9ab513ae1df5a7e1e62cfefcefe404637c063
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444566"
---
# <a name="a5---using-the-critical-directive"></a>A.5   Verwenden der critical-Direktive

Das folgende Beispiel schließt mehrere `critical` Directives ([Abschnitt 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18). Das Beispiel veranschaulicht ein Warteschlangen-Modell, bei der eine Aufgabe aus der Warteschlange entfernt und bearbeitet, werden. Um für mehrere Threads, die aus der Warteschlange entfernt der gleichen Aufgabe zu schützen, muss der entfernen-Vorgang einem `critical` Abschnitt. Da die zwei Warteschlangen in diesem Beispiel unabhängig sind, werden sie durch geschützt `critical` Anweisungen mit unterschiedlichen Namen *x-Achse enthält* und *Yaxis*.

```
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```