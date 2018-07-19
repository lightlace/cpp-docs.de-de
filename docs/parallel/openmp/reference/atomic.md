---
title: Atomic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf6287ff3c44d508a3e4293340e652edb201282f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694406"
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