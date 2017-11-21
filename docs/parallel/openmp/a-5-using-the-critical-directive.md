---
title: Die critical-Direktive mit a. 5 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ef678b58df9d2c323cdebb61feed52ebbaf607f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="a5---using-the-critical-directive"></a>A.5   Verwenden der critical-Direktive
Das folgende Beispiel schließt mehrere `critical` Direktiven ([Abschnitt 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) auf Seite 18). Das Beispiel veranschaulicht ein Warteschlangen-Modell, in dem eine Aufgabe aus der Warteschlange entfernt und gearbeitet wird. Abarbeiten der Warteschlange Vorgang muss zum Schutz gegen mehrere Threads, die daraus entfernt wird die gleiche Aufgabe einem `critical` Abschnitt. Da die zwei Warteschlangen in diesem Beispiel unabhängig sind, werden sie durch geschützt `critical` Richtlinien mit unterschiedlichen Namen *Xaxis* und *Yaxis*.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```