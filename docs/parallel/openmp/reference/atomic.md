---
title: Atomic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd00244d4668821942e7d6a9f6873652002bddb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="atomic"></a>atomisch
Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>Parameter  
 `expression`  
 Die Anweisung, die l-Wert, dessen Speicherort enthält mehrere Schreibvorgänge Schutz werden soll. Weitere Informationen zu gültiger Ausdruck Formen finden Sie unter der OpenMP-Spezifikation.  
  
## <a name="remarks"></a>Hinweise  
 Die `atomic` Richtlinie unterstützt kein OpenMP-Klauseln.  
  
 Weitere Informationen finden Sie unter [2.6.4 atomic erstellen](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)