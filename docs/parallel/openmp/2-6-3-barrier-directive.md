---
title: 2.6.3 Barrier-Direktive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68df92207feb45a77055098cdb1227a68b04bcab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="263-barrier-directive"></a>2.6.3 barrier-Anweisung
Die **Barriere** Richtlinie synchronisiert alle Threads in einem Team. Wenn festgestellt wird, wartet auf jeder Thread in das Team alle von den anderen diesen Punkt erreicht haben. Die Syntax der **Barriere** Richtlinie lautet wie folgt:  
  
```  
#pragma omp barrier new-line  
```  
  
 Nachdem alle Threads in das Team die Barriere erkannt wurden, beginnt jeder Thread in der Team die Anweisungen nach der Barrier-Direktive parallel ausführen. Beachten Sie, dass, weil die **Barriere** Richtlinie verfügt nicht über eine C-Language-Anweisung als Teil der Syntax, bestehen einige Einschränkungen auf die Platzierung innerhalb eines Programms. Finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik. Das folgende Beispiel veranschaulicht diese Einschränkungen.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```