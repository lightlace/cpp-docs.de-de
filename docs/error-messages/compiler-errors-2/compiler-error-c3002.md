---
title: "Compilerfehler C3002"
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
  - "C3002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3002"
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name1 Name2': Mehrere OpenMP\-Direktivennamen  
  
 Mehrere Direktivennamen sind nicht zulässig.  
  
 Im folgenden Beispiel wird C3002 generiert:  
  
```  
// C3002.c // compile with: /openmp int main() { #pragma omp parallel single   // C3002 }  
```