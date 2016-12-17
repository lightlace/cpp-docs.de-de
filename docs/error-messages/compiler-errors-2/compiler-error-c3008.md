---
title: "Compilerfehler C3008"
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
  - "C3008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3008"
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"arg": Im Argument der Direktive "Direktive" von OpenMP fehlt eine schließende "\)".  
  
 Eine OpenMP\-Direktive, die ein Argument akzeptiert, hatte keine schließende Klammer.  
  
 Im folgenden Beispiel wird C3008 generiert:  
  
```  
// C3008.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x   // C3008 // Try the following line instead: #pragma omp parallel shared(x) { } }  
```