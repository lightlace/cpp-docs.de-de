---
title: "Compilerfehler C3007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3007"
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Arg': Die Klausel für die 'Direktive'\-Direktive von OpenMP nimmt kein Argument an.  
  
 Eine OpenMP\-Direktive hat ein Argument aufgewiesen, aber die Direktive nimmt kein Argument an.  
  
 Im folgenden Beispiel wird C3007 generiert:  
  
```  
// C3007.c // compile with: /openmp int main() { #pragma omp parallel for ordered(2)   // C3007 }  
```