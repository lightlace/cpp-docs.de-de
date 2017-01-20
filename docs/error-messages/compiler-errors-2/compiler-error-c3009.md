---
title: "Compilerfehler C3009"
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
  - "C3009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3009"
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bezeichnung': Einsprung in strukturierten Block von OpenMP ist nicht zulässig.  
  
 Code kann nicht in einen oder aus einem OpenMP\-Block springen.  
  
 Im folgenden Beispiel wird C3009 generiert:  
  
```  
// C3009.c // compile with: /openmp int main() { #pragma omp parallel { lbl2:; } goto lbl2;   // C3009 }  
```