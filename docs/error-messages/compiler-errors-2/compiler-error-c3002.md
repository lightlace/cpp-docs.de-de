---
title: "Compilerfehler C3002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3002"
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name1 Name2': Mehrere OpenMP\-Direktivennamen  
  
 Mehrere Direktivennamen sind nicht zulässig.  
  
 Im folgenden Beispiel wird C3002 generiert:  
  
```  
// C3002.c // compile with: /openmp int main() { #pragma omp parallel single   // C3002 }  
```