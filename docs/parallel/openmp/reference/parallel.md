---
title: Parallele | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9293a70ce0615adf1e40bcb19b1706d9e39d4cca
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="parallel"></a>parallel
Definiert einen parallelen Bereich, also Code, die durch mehrere Threads parallel ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `clause` (optional)  
 NULL oder mehr Klauseln.  Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **parallele**.  
  
## <a name="remarks"></a>Hinweise  
 Die **parallele** Richtlinie unterstützt die folgenden OpenMP-Klauseln:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Parallele** kann auch verwendet werden, mit der [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md) und [für](../../../parallel/openmp/reference/for-openmp.md) Direktiven.  
  
 Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die Anzahl von Threads und Definieren eines parallelen Bereichs. Standardmäßig ist die Anzahl der Threads gleich der Anzahl der logischen Prozessoren auf dem Computer. Z. B. Wenn Sie einen Computer mit einem physischen Prozessor, die Hyperthreading aktiviert wurde verfügen, wird er zwei logischen Prozessoren und somit zwei Threads haben.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>Kommentar  
 Beachten Sie, dass die Reihenfolge der Ausgabe auf verschiedenen Computern variieren kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)