---
title: "Compilerfehler C3006"
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
  - "C3006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3006"
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klausel": In der Klausel für die "directive"\-Direktive von OpenMP fehlt ein erwartetes Argument.  
  
 Bei einer OpenMP\-Direktive fehlt ein erwartetes Argument.  
  
 Im folgenden Beispiel wird C3006 generiert:  
  
```  
// C3006.c // compile with: /openmp int main() { #pragma omp parallel shared   // C3006 // Try the following line instead: // #pragma omp parallel shared(x) {} }  
```