---
title: "A.26   Using the threadprivate Directive"
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
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.26   Using the threadprivate Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgenden Beispiele veranschaulichen, wie die `threadprivate`\-Direktive \([2.7.1 Abschnitt](../../parallel/openmp/2-7-1-threadprivate-directive.md) auf Seite 23\) verwendet, um jedem Thread einen separaten Indikator zu vermitteln.  
  
 **Beispiel 1:**  
  
```  
int counter = 0;  
#pragma omp threadprivate(counter)  
  
int sub()  
{  
    counter++;  
    return(counter);  
}  
```  
  
 **Beispiel 2:**  
  
```  
int sub()  
{  
    static int counter = 0;  
    #pragma omp threadprivate(counter)  
    counter++;  
    return(counter);  
}  
```