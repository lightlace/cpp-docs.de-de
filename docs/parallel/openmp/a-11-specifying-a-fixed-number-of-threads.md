---
title: Festlegen einer festen Anzahl von Threads A.11 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71d09c470b76b61c6737566f7833334aeec6c63a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Angeben einer festgelegten Anzahl von Threads
Einige Programme basieren auf einer festen, vordefinierten Anzahl von Threads ordnungsgemäß ausgeführt.  Da die Standardeinstellung für die dynamische Anpassung der Anzahl von Threads Implementierung definiert ist, können diese Programme deaktivieren Sie die dynamische Threads-Funktion, und legen Sie die Anzahl der Threads explizit, um Portabilität sicherzustellen. Im folgende Beispiel wird gezeigt, wie Sie diesen Vorgang mit `omp_set_dynamic` ([Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39), und `omp_set_num_threads` ([Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 In diesem Beispiel wird das Programm ordnungsgemäß ausgeführt, nur dann, wenn er vom 16 Threads ausgeführt wird. Ist die Implementierung nicht 16 Threads unterstützen kann, ist das Verhalten dieses Beispiels mit der Implementierung definiert.  
  
 Beachten Sie, dass die Anzahl der Threads, die Ausführung eines parallelen Bereichs während eines parallelen Bereichs ist, unabhängig von der Einstellung "Threads" dynamische konstant bleibt. Der Mechanismus für die dynamische Threads bestimmt die Anzahl der Threads an, die am Anfang des parallelen Bereichs verwenden und bleibt sie konstant für die Dauer des Bereichs.