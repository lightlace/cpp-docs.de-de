---
title: Omp_set_nested | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6539167b936efdc4c9f407cd951c9c582b0a138
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="ompsetnested"></a>omp_set_nested
Ermöglicht das geschachtelte Parallelität.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `val`  
 Wert ungleich NULL ist, können geschachtelte Parallelität. Wenn 0 (null), deaktiviert geschachtelte Parallelität.  
  
## <a name="remarks"></a>Hinweise  
 Geschachtelte OMP Parallelität mit aktiviert werden kann `omp_set_nested`, oder durch Festlegen der [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) -Umgebungsvariablen angegeben.  
  
 Die Einstellung für `omp_set_nested` überschreibt die Einstellung von der `OMP_NESTED` -Umgebungsvariablen angegeben.  
  
 Wenn aktiviert, kann die Umgebungsvariable ein andernfalls operational Programm unterbrechen, da die Anzahl der Threads sich exponentiell beim Schachteln von paralleler Regions erhöht.  Z. B. eine Funktion, dass rekursiv 6 Mal klicken Sie mit der Anzahl von OMP-Threads auf 4 festgelegt erfordert 4.096 (4, um die Leistungsfähigkeit von 6) im Allgemeinen threads, die Leistung Ihrer Anwendung beeinträchtigt wird, überschreitet die Anzahl der Threads die Anzahl der Prozessoren. Einzige Ausnahme hierbei wäre, dass e/a Anwendungen gebunden.  
  
 Verwendung [Omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) die aktuelle Einstellung der anzuzeigenden `omp_set_nested`.  
  
 Weitere Informationen finden Sie unter [3.1.9 Omp_set_nested-Funktion](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)