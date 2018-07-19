---
title: einzelne | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dd5349331ac23998511a8f1b838d2cd13b01998
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691858"
---
# <a name="single"></a>Einfach
Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt der master-Thread ausgeführt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>Parameter  
 `clause` (optional)  
 NULL oder mehr Klauseln. Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **einzelne**.  
  
## <a name="remarks"></a>Hinweise  
 Die **einzelne** Richtlinie unterstützt die folgenden OpenMP-Klauseln:  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 Die [master](../../../parallel/openmp/reference/master.md) Richtlinie können Sie angeben, dass ein Abschnitt des Codes nur für die master-Thread ausgeführt werden sollen.  
  
 Weitere Informationen finden Sie unter [2.4.3 einzelne erstellen](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)