---
title: OpenMP-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01967e47d8108803fdadd9c9cfe746a4d477459
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-functions"></a>OpenMP-Funktionen
Enthält Links zu den Funktionen, die in der OpenMP-API verwendet.  
  
 Die Visual C++-Implementierung der OpenMP-standard umfasst die folgenden Funktionen.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Hebt die Initialisierung einer Sperre.|  
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Hebt die Initialisierung einer omp_nest_lock_t-Sperre.|  
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Gibt einen Wert, der angibt, wenn die Anzahl der Threads, die in nachfolgenden parallelen Bereich verfügbar, die von der Laufzeit angepasst werden kann.|  
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Gibt eine ganze Zahl, die gleich oder größer als die Anzahl der Threads, die verfügbar sind, wenn einem parallelen Bereich ohne [Num_threads](../../../parallel/openmp/reference/num-threads.md) an diesem Punkt im Code definiert wurden.|  
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Gibt einen Wert, der angibt, ob geschachtelte Parallelität aktiviert ist.|  
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Gibt die Anzahl der Prozessoren, die verfügbar sind, wenn die Funktion aufgerufen wird.|  
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Gibt die Anzahl der Threads in der parallelen Bereichs zurück.|  
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Gibt die Thread-Anzahl der ausgeführten Threads innerhalb Hashteams Thread zurück.|  
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|Gibt die Anzahl der Sekunden zwischen den Teilstrichen Prozessor zurück.|  
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Gibt ein Wert in Sekunden für die Zeit von einem bestimmten Punkt vergangen sind.|  
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Gibt einen Wert ungleich NULL, wenn innerhalb eines parallelen Bereichs aufgerufen.|  
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Initialisiert eine einfache Sperre.|  
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Initialisiert eine Sperre.|  
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Gibt an, dass die Anzahl der Threads, die in nachfolgenden parallelen Bereich zur Verfügung stehen, von der Laufzeit angepasst werden kann.|  
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Blöcke thread Ausführung, bis eine Sperre verfügbar ist.|  
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Blöcke thread Ausführung, bis eine Sperre verfügbar ist.|  
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Ermöglicht das geschachtelte Parallelität.|  
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Die Anzahl der Threads in nachfolgenden parallele Regionen, legt fest, es sei denn, durch Überschreiben einer [Num_threads](../../../parallel/openmp/reference/num-threads.md) Klausel.|  
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Versucht, eine Sperre festzulegen, aber nicht die Ausführung des Threads blockiert.|  
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Versucht, eine Sperre omp_nest_lock_t festzulegen, jedoch nicht blockiert die Ausführung des Threads.|  
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Gibt eine Sperre frei.|  
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Gibt eine omp_nest_lock_t-Sperre frei.|  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksverweis](../../../parallel/openmp/reference/openmp-library-reference.md)