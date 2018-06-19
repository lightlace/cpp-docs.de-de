---
title: Beispiele für die geordnete Direktive A.23 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37cc4ea9db8cbd1a7bf095e2bde0ae482053a584
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692748"
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