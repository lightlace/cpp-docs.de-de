---
title: "A.23   Examples of the ordered Directive"
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
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.23   Examples of the ordered Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es ist möglich, mehrere geordnete Abschnitte mit `for` verfügen, das der `ordered`\-Klausel angegeben wird.  Im ersten Beispiel ist inkompatibel, da die API Folgendes angegeben wird:  
  
 „Eine Iteration einer Schleife mit einem `for` Konstrukt darf die gleichen `ordered`\-Direktive nicht mehrmals ausführen, und sie dürfen nicht mehr als eine `ordered`\-Direktive ausführen“. \(Siehe [2.6.6 Abschnitt](../../parallel/openmp/2-6-6-ordered-construct.md) auf Seite 22\)  
  
 In diesem nicht kompatiblen Beispiel werden alle Iterationen 2 geordnete Abschnitte aus:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 Im Folgenden kompatible Beispiel wird `for` mit mehr als einem geordneten Abschnitts veranschaulicht:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```