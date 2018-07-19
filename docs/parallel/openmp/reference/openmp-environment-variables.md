---
title: OpenMP-Umgebungsvariablen | Microsoft Docs
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
ms.openlocfilehash: 02248b7725f2a4312f26984c798e7248463d2615
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692307"
---
# <a name="openmp-environment-variables"></a>OpenMP-Umgebungsvariablen
Enthält Links zu Umgebungsvariablen in der OpenMP-API verwendet.  
  
 Die Visual C++-Implementierung der OpenMP-standard umfasst die folgenden Umgebungsvariablen. Diese Umgebungsvariablen werden gelesen, beim Programmstart und Änderungen auf ihre Werte werden zur Laufzeit ignoriert (z. B. [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|Umgebungsvariable|Beschreibung|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Gibt an, ob die OpenMP zur Laufzeit die Anzahl der Threads in einem parallelen Bereich anpassen kann.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Gibt an, ob geschachtelte Parallelität aktiviert ist, es sei denn, geschachtelte Parallelität aktiviert oder deaktiviert ist, `omp_set_nested`.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Legt die maximale Anzahl von Threads in den parallelen Bereich, es sei denn, durch Überschreiben [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [Num_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Verändert das Sitzungsverhalten, sodass die [Zeitplan](../../../parallel/openmp/reference/schedule.md) Klausel bei `schedule(runtime)` angegeben ist, eine `for` oder `parallel for` Richtlinie.|  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksverweis](../../../parallel/openmp/reference/openmp-library-reference.md)