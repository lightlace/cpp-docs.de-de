---
title: Abschnitte (OpenMP) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- section
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9cdc8a79f95f2a2a4dee3c43c067177f0924b46f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="sections-openmp"></a>sections (OpenMP)
Identifiziert die Codeabschnitte auf allen Threads aufgeteilt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `clause` (optional)  
 NULL oder mehr Klauseln. Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **Abschnitte**.  
  
## <a name="remarks"></a>Hinweise  
 Die **Abschnitte** Richtlinie darf null oder mehr **Abschnitt** Direktiven.  
  
 Die **Abschnitte** Richtlinie unterstützt die folgenden OpenMP-Klauseln:  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 Wenn **parallele** ebenfalls angegeben wird, `clause` kann jede beliebige Klausel vom akzeptiert die **parallele** oder **Abschnitte** Direktiven, mit Ausnahme von `nowait`.  
  
 Weitere Informationen finden Sie unter [2.4.2 sections-Konstrukt](../../../parallel/openmp/2-4-2-sections-construct.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)