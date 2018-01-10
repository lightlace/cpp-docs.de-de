---
title: 3.1.3 Omp_get_max_threads-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13aee27dc04afb8414a89bb8f30a98c8e73fb694
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads-Funktion
Die **Omp_get_max_threads** Funktion gibt eine ganze Zahl, die garantiert ist, mindestens so groß wie die Anzahl der Threads, die verwendet wird, um ein Team bilden, wenn einem parallelen Bereich ohne eine **Num_threads** Klausel an diesem Punkt im Code auftreten würden. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Die folgenden drückt eine Untergrenze für den Wert der **Omp_get_max_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Beachten Sie, dass wenn eine nachfolgende parallelen Bereichs verwendet die **Num_threads** -Klausel, um eine bestimmte Anzahl von Threads, die Garantie für die untere Grenze des Ergebnisses anfordern **Omp_get_max_threads** keine langen enthält.  
  
 Die **Omp_get_max_threads** Rückgabewert der Funktion ausreichend Speicherplatz für alle Threads in das Team auf den nachfolgenden parallelen Bereich gebildet dynamisch zuordnen verwendet werden kann.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **Omp_get_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.  
  
-   **Omp_set_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.  
  
-   **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".