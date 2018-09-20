---
title: OpenMP-Klauseln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd0a8f66f9b0d027671629998597955b3aa69e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378325"
---
# <a name="openmp-clauses"></a>OpenMP-Klauseln

Enthält Links zu den Klauseln, die in der OpenMP-API verwendet.

Visual C++ unterstützt die folgenden OpenMP-Klauseln:

|Klausel|Beschreibung|
|------------|-----------------|
|[copyin](../../../parallel/openmp/reference/copyin.md)|Ermöglicht die Threads der master-Thread-Wert, für den Zugriff auf eine [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) Variable.|
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Gibt an, dass eine oder mehrere Variablen, die auf allen Threads freigegeben werden soll.|
|[default](../../../parallel/openmp/reference/default-openmp.md)|Gibt das Verhalten ohne bereichseinschränkung Variablen in einem parallelen Bereich an.|
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll, und die Variable mit dem Wert der Variablen initialisiert werden soll, da sie vor dem das parallele Konstrukt vorhanden ist.|
|[if](../../../parallel/openmp/reference/if-openmp.md)|Gibt an, ob eine Schleife parallel oder seriell ausgeführt werden soll.|
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Gibt an, dass der umschließenden Kontext Version der Variablen ist gleich der privaten Version der Thread der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte) ausgeführt wird.|
|[nowait](../../../parallel/openmp/reference/nowait.md)|Überschreibt die Grenze, die in einer Anweisung implizit.|
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|Legt die Anzahl der Threads in einem Team Thread fest.|
|[Sortiert](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Erforderlich für eine parallele [für](../../../parallel/openmp/reference/for-openmp.md) Anweisung Wenn ein [sortiert](../../../parallel/openmp/reference/ordered-openmp-directives.md) -Direktive ist, in der Schleife verwendet werden.|
|[private](../../../parallel/openmp/reference/private-openmp.md)|Gibt an, dass jeder Thread eine eigene Instanz einer Variablen zugewiesen werden soll.|
|[reduction](../../../parallel/openmp/reference/reduction.md)|Gibt an, dass eine oder mehrere Variablen, die für jeden Thread privat sind ein Reduzierungsvorgang am Ende des parallelen Bereichs werden.|
|[schedule](../../../parallel/openmp/reference/schedule.md)|Gilt für die [für](../../../parallel/openmp/reference/for-openmp.md) Richtlinie.|
|[Freigegebene](../../../parallel/openmp/reference/shared-openmp.md)|Gibt an, dass eine oder mehrere Variablen, die auf allen Threads freigegeben werden soll.|

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)