---
title: "Compilerfehler C3018"
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
  - "C3018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3018"
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var1": Der Test oder das Inkrement in der For\-Anweisung von OpenMP muss die Indexvariable "var2" verwenden.  
  
 Eine `for`\-Schleife in einer OpenMP\-Anweisung muss dieselbe Variable für ihren Test und ihr Inkrement wie für ihren Index verwenden.  
  
 Im folgenden Beispiel wird C3018 generiert:  
  
```  
// C3018.cpp // compile with: /openmp int main() { int i = 0, j = 5; #pragma omp parallel { #pragma omp for for (i = 0; j < 10; ++i)   // C3018 // try the the following line instead // for (i = 0; i < 10; ++i) j *= 2; #pragma omp for for (i = 0; i < 10; j = j + i)   // C3018 // try the the following line instead // for (i = 0; i < 10; i = j + i) j *= 2; } }  
```