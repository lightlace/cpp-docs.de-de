---
title: Omp_set_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_dynamic
dev_langs: C++
helpviewer_keywords: omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13cb098170e46b8459821156aeb8be369bbc1ffa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Gibt an, dass die Anzahl der Threads, die in nachfolgenden parallelen Bereich zur Verfügung stehen, von der Laufzeit angepasst werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `val`  
 Ein Wert, der angibt, ob die Anzahl der Threads, die in nachfolgenden parallelen Bereich verfügbar, die von der Laufzeit angepasst werden kann.  Wert ungleich NULL, die Common Language Runtime die Anzahl der Threads, wenn der Wert 0 anpassen kann, werden die Common Language Runtime die Anzahl der Threads nicht dynamisch angepasst.  
  
## <a name="remarks"></a>Hinweise  
 Die Anzahl von Threads wird von festgesetzten Wert nie übersteigen [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Verwendung [Omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) die aktuelle Einstellung der anzuzeigenden `omp_set_dynamic`.  
  
 Die Einstellung für `omp_set_dynamic` überschreibt die Einstellung von der [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) -Umgebungsvariablen angegeben.  
  
 Weitere Informationen finden Sie unter [3.1.7 Omp_set_dynamic-Funktion](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)