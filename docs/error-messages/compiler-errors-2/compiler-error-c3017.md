---
title: "Compilerfehler C3017"
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
  - "C3017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3017"
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Beendigungstest in der For\-Anweisung von OpenMP weist eine ungültige Form auf.  
  
 Eine `for`\-Schleife in einer OpenMP\-Anweisung muss vollständig und explizit angegeben werden.  
  
 Im folgenden Beispiel wird C3017 generiert.  
  
```  
// C3017.cpp // compile with: /openmp int main() { int i = 0, j = 10; #pragma omp parallel { #pragma omp for for (i = 0; i; ++i)   // C3017 // Try the following line instead: // for (i = 0; i < 10; ++i) ; } }  
```