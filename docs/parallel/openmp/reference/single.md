---
title: einzelne | Microsoft-Dokumentation
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
ms.openlocfilehash: 7ff1a255933b79d39b6eedbb9362ff76a34e0f8a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716988"
---
# <a name="single"></a>Einfach
Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt die master-Thread ausgeführt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>Parameter  

`clause`  
(Optional) NULL oder mehr Klauseln. Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **einzelne**.  
  
## <a name="remarks"></a>Hinweise  
 Die **einzelne** -Anweisung unterstützt die folgenden OpenMP-Klauseln:  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 Die [master](../../../parallel/openmp/reference/master.md) -Direktive können Sie angeben, dass ein Abschnitt des Codes nur für die master-Thread ausgeführt werden sollen.  
  
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