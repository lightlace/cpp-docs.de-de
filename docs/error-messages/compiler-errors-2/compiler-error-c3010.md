---
title: "Compilerfehler C3010"
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
  - "C3010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3010"
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichnung': Aussprung aus strukturiertem Block von OpenMP ist nicht zulässig.  
  
 Code kann nicht in einen oder aus einem OpenMP\-Block springen.  
  
 Im folgenden Beispiel wird C3010 generiert:  
  
```  
// C3010.c // compile with: /openmp int main() { #pragma omp parallel { #pragma omp parallel { goto lbl3; } } lbl3:;   // C3010 }  
```