---
title: Omp_get_wtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_wtime
dev_langs: C++
helpviewer_keywords: omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c9a4d66789a94e30c2562c5a6d071cab1012b32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ompgetwtime"></a>omp_get_wtime
Gibt ein Wert in Sekunden für die Zeit von einem bestimmten Punkt vergangen sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
double omp_get_wtime( );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt zurück, dass einige beliebige jedoch konsistent zeigen ein Wert in Sekunden Zeit vergangen ist.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Punkt wird während der Ausführung des Programms, sodass nachfolgende Vergleiche konsistent bleiben.  
  
 Weitere Informationen finden Sie unter [3.3.1 Omp_get_wtime-Funktion](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
```Output  
start = 594255.3671159324  
end = 594256.3664474116  
diff = 0.9993314791936427  
wtick = 2.793651148400146e-007  
1/wtick = 3579545  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)