---
title: "Beispiele für die geordnete Direktive A.23 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Beispiele für die ordered-Direktive
Es ist möglich, mehrere geordnete Abschnitte mit einer `for` angegeben mit der `ordered` Klausel. Im erste Beispiel ist nicht kompatibel, da die API gibt Folgendes an:  
  
 "Eine Iteration einer Schleife mit einer `for` Konstrukt muss nicht ausgeführt, die gleiche `ordered` Richtlinie mehr als einmal, und es muss nicht ausgeführt, mehr als eine `ordered` Richtlinie." (Siehe [Abschnitt 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) auf der Seite "22")  
  
 In diesem Beispiel nicht kompatible führen alle Iterationen 2 geordnete Abschnitte:  
  
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
  
 Kompatible Folgendes Beispiel eine `for` mit mehr als einem sortiert Abschnitt:  
  
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