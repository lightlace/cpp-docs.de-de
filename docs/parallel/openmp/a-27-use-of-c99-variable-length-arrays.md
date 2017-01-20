---
title: "A.27   Use of C99 Variable Length Arrays"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.27   Use of C99 Variable Length Arrays
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird veranschaulicht, wie C99 Arrays variabler Länge \(VLAs\) in `firstprivate`\-Direktive \([2.7.2.2 Abschnitt](../../parallel/openmp/2-7-2-2-firstprivate.md) auf Seite 26\).  
  
> [!NOTE]
>  Arrays mit variabler Länge werden nicht nur in Visual C\+\+ unterstützt.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```