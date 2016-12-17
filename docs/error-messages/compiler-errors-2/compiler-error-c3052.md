---
title: "Compilerfehler C3052"
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
  - "C3052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3052"
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Var": Die Variable wird in einer Datenfreigabeklausel nicht unter einer default\(none\)\-Klausel angezeigt.  
  
 Wenn [default\(none\)](../../parallel/openmp/reference/default-openmp.md) verwendet wird, muss jede in einem strukturierten Block verwendete Variable explizit als [shared](../../parallel/openmp/reference/shared-openmp.md) oder [private](../../parallel/openmp/reference/private-openmp.md) angegeben werden.  
  
 Im folgenden Beispiel wird C3052 generiert.  
  
```  
// C3052.cpp // compile with: /openmp /c int main() { int n1 = 1; #pragma omp parallel default(none) // shared(n1) private(n1) { n1 = 0;   // C3052 use either a shared or private clause } }  
```