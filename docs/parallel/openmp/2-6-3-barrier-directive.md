---
title: "2.6.3 barrier Directive"
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
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.3 barrier Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Barriere**\-Direktive synchronisieren alle Threads in einem Team.  Wenn er festgestellt wird, wird jeder Thread im Team, bis alle anderen diesen Punkt erreicht haben.  Die Syntax der **Barriere**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp barrier new-line  
```  
  
 Schließlich haben Threads im Team die Barriere erreicht, jeder Thread im Team beginnt, die nach den Anweisungen direktiven Barrieren parallel ausgeführt werden.  Da die **Barriere**\-Direktive Wechselstrom\-Sprachanweisung nicht als Teil der Syntax haben, jedoch einige Einschränkungen bezüglich ihrer Platzierung innerhalb eines Programms vorhanden ist.  Weitere Informationen finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik.  Das folgende Beispiel verdeutlicht diese Einschränkungen.  
  
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