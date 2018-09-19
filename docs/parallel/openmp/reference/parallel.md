---
title: Parallele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c8b1466eae343b6c644b6ecfbd919c3241259bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705964"
---
# <a name="parallel"></a>parallel
Definiert einen parallelen Bereich, also Code, die von mehreren Threads gleichzeitig ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="arguments"></a>Argumente

*Klausel*<br/>
(Optional) NULL oder mehr Klauseln.  Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **parallele**.  
  
## <a name="remarks"></a>Hinweise  
 Die **parallele** -Anweisung unterstützt die folgenden OpenMP-Klauseln:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [Freigegebene](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Parallele** kann auch verwendet werden, mit der [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md) und [für](../../../parallel/openmp/reference/for-openmp.md) Anweisungen.  
  
 Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht die legen Sie die Anzahl von Threads und ein paralleles Bereichs zu definieren. Standardmäßig entspricht die Anzahl der Threads auf die Anzahl der logischen Prozessoren auf dem Computer. Z. B. Wenn Sie einen Computer mit einem physischen Prozessor, die Hyperthreading aktiviert wurde verfügen, wird es zwei logischen Prozessoren und damit zwei Threads haben.  
  
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