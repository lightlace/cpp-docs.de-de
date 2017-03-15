---
title: "Compilerwarnung (Stufe 4) C4130 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4130"
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Operator": Logische Operation mit Adresse einer Zeichenfolgenkonstanten  
  
 Das Verwenden des Operators mit der Adresse eines Zeichenfolgenliterals erzeugt unerwarteten Code.  
  
 Im folgenden Beispiel wird C4130 generiert.  
  
```  
// C4130.cpp // compile with: /W4 int main() { char *pc; pc = "Hello"; if (pc == "Hello") // C4130 { } }  
```  
  
 Die **if**\-Anweisung vergleicht den im Zeiger `pc` gespeicherten Wert mit der Adresse der Zeichenfolge "Hello", die bei jedem Vorkommen der Zeichenfolge im Code separat zugewiesen wird. Die **if** Anweisung vergleicht nicht die Zeichenfolge, auf die von `pc` gezeigt wird, mit der Zeichenfolge "Hello".  
  
 Verwenden Sie zum Vergleichen von Zeichenfolgen die `strcmp`\-Funktion.