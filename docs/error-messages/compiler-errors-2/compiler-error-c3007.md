---
title: "Compilerfehler C3007"
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
  - "C3007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3007"
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Arg': Die Klausel für die 'Direktive'\-Direktive von OpenMP nimmt kein Argument an.  
  
 Eine OpenMP\-Direktive hat ein Argument aufgewiesen, aber die Direktive nimmt kein Argument an.  
  
 Im folgenden Beispiel wird C3007 generiert:  
  
```  
// C3007.c // compile with: /openmp int main() { #pragma omp parallel for ordered(2)   // C3007 }  
```