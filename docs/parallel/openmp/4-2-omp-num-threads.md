---
title: 4.2 OMP_NUM_THREADS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9996a09661d962eb5e936fdb484c9dd534e46904
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445190"
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS

Die **OMP_NUM_THREADS** Umgebungsvariable wird die Standardanzahl von Threads zur Verwendung während der Ausführung aus, es sei denn, diese Zahl explizit, durch den Aufruf geändert wird der **Omp_set_num_threads** Bibliotheksroutine oder durch eine explizite **Num_threads** -Klausel für eine **parallele** Richtlinie.

Der Wert des der **OMP_NUM_THREADS** -Umgebungsvariable muss eine positive ganze Zahl sein. Die Auswirkungen hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Für einen umfassenden Satz von Regeln über die Interaktion zwischen der **OMP_NUM_THREADS** Umgebung Variable und die dynamische Anpassung der Threads, siehe Abschnitt 2.3 auf Seite 8.

Wenn kein Wert, für angegeben wird die **OMP_NUM_THREADS** Umgebungsvariablen, oder wenn der angegebene Wert eine positive ganze Zahl ist, oder wenn der Wert größer als die maximale Anzahl von Threads ist das System kann zu unterstützen, die Anzahl der zu verwendenden Threads ist die Implementierung definiert.

Beispiel:

```
setenv OMP_NUM_THREADS 16
```

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **Omp_set_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf 36.

- **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.