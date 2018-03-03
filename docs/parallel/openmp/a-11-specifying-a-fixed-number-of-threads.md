---
title: Festlegen einer festen Anzahl von Threads A.11 | Microsoft Docs
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
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72c8aca2b90f021771ba9f9fc8a86d784ffe24a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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