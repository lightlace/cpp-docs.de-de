---
title: "A.8   Specifying Parallel Sections"
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
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.8   Specifying Parallel Sections
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel [2.4.2 Abschnitt](../../parallel/openmp/2-4-2-sections-construct.md) \(für *Xaxis*auf Seite 14\) funktioniert, *Yaxis*und *Zaxis* können gleichzeitig ausgeführt werden.  Die ersten `section`\-Direktiven sind optional.  Beachten Sie, dass alle `section`\-Direktive im lexikalischen Wertebereich des Konstrukts `parallel``sections` angezeigt wird.  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```