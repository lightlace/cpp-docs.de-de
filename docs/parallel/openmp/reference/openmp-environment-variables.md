---
title: OpenMP-Umgebungsvariablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b61535fd07066c4a1ee24658fdfe81047efc90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446568"
---
# <a name="openmp-environment-variables"></a>OpenMP-Umgebungsvariablen

Enthält Links zu den Umgebungsvariablen, die in der OpenMP-API verwendet.

Die Visual C++-Implementierung von der OpenMP-standard umfasst die folgenden Umgebungsvariablen. Diese Umgebungsvariablen werden gelesen, beim Programmstart und Änderungen an deren Werte zur Laufzeit ignoriert werden (z. B. [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Umgebungsvariable|Beschreibung|
|--------------------------|-----------------|
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.|
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.|
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Legt die maximale Anzahl von Threads in den parallelen Bereich fest, es sei denn, durch außer Kraft gesetzt [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [Num_threads](../../../parallel/openmp/reference/num-threads.md).|
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Ändert das Verhalten von der [Zeitplan](../../../parallel/openmp/reference/schedule.md) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.|

## <a name="see-also"></a>Siehe auch

[Referenz zur Bibliothek](../../../parallel/openmp/reference/openmp-library-reference.md)