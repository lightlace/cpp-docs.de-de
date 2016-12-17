---
title: "Compilerfehler C3003"
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
  - "C3003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3003"
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Direktive': Nach Direktivenklauseln ist kein OpenMP\-Direktivenname zulässig.  
  
 Ein OpenMP\-Direktivenname darf nicht auf eine OpenMP\-Direktivenklausel folgen.  
  
 Im folgenden Beispiel wird C3003 generiert:  
  
```  
// C3003.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x, y, z) for   // C3003 }  
```