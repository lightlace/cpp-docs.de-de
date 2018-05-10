---
title: Einzelne 9 Dokumentieren Using-Direktiven | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc0e0e08b0b7bdea05bf4c627ae33cc42298c6dc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="a9---using-single-directives"></a>A.9   Verwenden einzelner Direktiven
Das folgende Beispiel veranschaulicht die `single` Richtlinie ([Abschnitt 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) auf Seite "15"). Im Beispiel nur ein Thread (in der Regel der erste Thread, der erkennt die `single` Richtlinie) fortschrittsmeldung druckt. Der Benutzer muss keine Annahmen wie auszuführende Bestimmung des Threads wird die `single` Abschnitt. Alle anderen Threads überspringt die `single` Abschnitt, und beenden Sie die Grenze am Ende der `single` erstellen. Wenn andere Threads fortgesetzt werden können, ohne zu warten, der vom Thread ausgeführten der `single` Abschnitt eine `nowait` -Klausel angegeben werden kann, auf die `single` Richtlinie.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```