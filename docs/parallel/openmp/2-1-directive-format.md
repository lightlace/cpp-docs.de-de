---
title: 2.1 Direktivenformat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3ff4e0078ffd086ce3b62d8927184188f0ebdd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="21-directive-format"></a>2.1 Anweisungsformat
Die Syntax für eine Direktive von OpenMP wird offiziell angegeben, indem die Grammatik in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md), informell wie folgt:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Jede Direktive beginnt mit **#pragma Omp**, um potenzielle Konflikte mit anderen (nicht-OpenMP oder Hersteller Erweiterungen mit OpenMP) pragma-Direktiven mit den gleichen Namen zu reduzieren. Der Rest der Anweisung folgt die Konventionen der C- und C++-Standards für Compilerdirektiven. Insbesondere Leerraum genutzt werden vor und nach der  **#** , und manchmal Leerzeichen zum Trennen Sie die Wörter in einer Anweisung verwendet werden muss. Vorverarbeitungstoken nach der **#pragma Omp** makroersetzung unterliegen.  
  
 Direktiven sind Groß-/Kleinschreibung beachtet. Die Reihenfolge der Klauseln in Direktiven spielt keine. Klauseln auf Direktiven können wiederholt werden, unterliegen den oben angegebenen, in der Beschreibung der einzelnen Klauseln Einschränkungen bei Bedarf. Wenn *Variablenliste* wird in einer Klausel nur Variablen angegeben werden muss. Nur ein *Richtlinie-Name* pro Direktive kann angegeben werden.  Die folgende Anweisung ist z. B. nicht zulässig:  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 Eine OpenMP-Direktive gilt für höchstens eine nachfolgende-Anweisung, die einem strukturierten Block sein muss.