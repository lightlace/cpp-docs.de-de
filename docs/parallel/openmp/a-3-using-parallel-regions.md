---
title: Verwenden von parallelen Bereichen a. 3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be3489e924dab7faa50d26c7cb89af67b4034ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a3---using-parallel-regions"></a>A.3   Verwenden von parallelen Bereichen
Die `parallel` Richtlinie ([Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8") kann in gröbere parallele Programme verwendet werden. Im folgenden Beispiel jeder Thread in den parallelen Bereich entscheidet, welcher Teil der globalen Array `x` arbeiten auf, basierend auf der Anzahl der Threads:  
  
```  
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)  
{  
    iam = omp_get_thread_num();  
    np =  omp_get_num_threads();  
    ipoints = npoints / np;  
    subdomain(x, iam, ipoints);  
}  
```