---
title: 3.1.2 Omp_get_num_threads-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d595fd47b87bbc3fd7701fc847821c73169a23e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads-Funktion
Die **Omp_get_num_threads** Funktion gibt die Anzahl der Threads derzeit im Team, die Ausführung des parallelen Bereichs aus der sie aufgerufen wird. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 Die **Num_threads** -Klausel, die **Omp_set_num_threads** -Funktion und die **OMP_NUM_THREADS** Umgebungsvariable steuern die Anzahl der Threads in einem Team.  
  
 Wenn die Anzahl der Threads explizit nicht vom Benutzer festgelegt wurde, ist die Standardeinstellung Implementierung definiert. Diese Funktion auf der nächsten einschließenden bindet **parallele** Richtlinie. Diese Funktion gibt 1 zurück, wenn der Aufruf aus einem seriellen Teil eines Programms oder eines geschachtelten parallelen Bereichs, das serialisiert wird.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **OMP_NUM_THREADS** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48.  
  
-   **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".  
  
-   **Parallele** erstellen, finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".