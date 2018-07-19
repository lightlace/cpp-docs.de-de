---
title: Mithilfe der atomic-Direktive A.12 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 719d7a9843a0759b5a5bd558e07a2004f9ef1543
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691408"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Verwenden der atomic-Direktive
Im folgende Beispiel vermeidet Racebedingungen (gleichzeitige Aktualisierung eines Elements *x* durch mehrere Threads) mithilfe der `atomic` Richtlinie ([Abschnitt 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) auf Seite "19"):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 Der Vorteil der Verwendung der `atomic` -Direktive in diesem Beispiel ist, dass Updates von zwei verschiedenen Elementen eines x parallel erfolgen können. Wenn eine `critical` Richtlinie ([Abschnitt 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18) stattdessen verwendet wurden, und klicken Sie dann alle updates für Elemente des *x* würde seriell (jedoch nicht in einer Reihenfolge garantiert) ausgeführt werden.  
  
 Beachten Sie, dass die `atomic` Richtlinie gilt nur für die C- oder C++-Anweisung unmittelbar folgt.  Daher Elemente *y* in diesem Beispiel werden nicht automatisch aktualisiert.