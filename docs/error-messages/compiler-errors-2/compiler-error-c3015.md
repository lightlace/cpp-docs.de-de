---
title: "Compilerfehler C3015"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3015"
ms.assetid: d5e8e50b-7542-4b2d-8665-1b22072a5bc6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Initialisierung in der For\-Anweisung von OpenMP weist eine ungültige Form auf.  
  
 Eine `for`\-Schleife in einer OpenMP\-Anweisung muss vollständig und explizit angegeben werden.  
  
 Im folgenden Beispiel wird C3015 generiert:  
  
```  
// C3015.cpp // compile with: /openmp int main() { int i = 0, j = 10; #pragma omp parallel { #pragma omp for for (; i < 0; i += j)   // C3015 // Try the following line instead: // for (i = 0; i < 0; i++) --j; } }  
```