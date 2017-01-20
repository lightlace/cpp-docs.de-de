---
title: "2.1 Directive Format"
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
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.1 Directive Format
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Syntax OpenMP\-Direktive formal wird durch die Grammatik in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)und informell angegeben, wie folgt:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Startet den einzelnen Direktiven mit **\#pragma omp**, das Potenzial für Konflikt mit anderen Anbieters oder OpenMP \(Nicht Erweiterungen zu OpenMP\) \- Pragma direktiven mit demselben Namen zu reduzieren.  Der Rest der Direktiven folgt den Konventionen der C\- und C\+\+\-Standards für die Compilerdirektive.  Insbesondere können Leerzeichen vor und nach **\#**verwendet werden, und in einigen Fällen müssen Leerräume verwendet werden, um die Wörter in Direktive zu trennen.  Die Vorverarbeitungs, die **\#pragma omp** token durchführen, unterliegen die Makros.  
  
 \- Direktive muss die Groß\-\/Kleinschreibung beachtet werden.  Die Reihenfolge der Klauseln in der Direktive angezeigt werden, ist nicht wichtig.  Klauseln nach Bedarf auf Direktive werden je nach den Einschränkungen überprüft werden, die in der Beschreibung jeder FROM\-Klausel aufgeführt sind.  Wenn *Variable Liste* in einer FROM\-Klausel angezeigt wird, muss sie nur Variablen angeben.  *Zeichenname* darf nur ein *Direktive* pro \- Direktive angegeben sind.  Beispielsweise werden die folgenden Direktiven nicht zulässig:  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP\-Direktive gelten für höchstens eine folgende Anweisung an, die ein strukturierter Block sein muss.