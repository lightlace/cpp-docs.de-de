---
title: "Compilerfehler C3011"
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
  - "C3011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3011"
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Inlineassembly direkt innerhalb eines parallelen Bereichs ist nicht zulässig.  
  
 Ein paralleler `omp`\-Bereich darf keine Inlineassemblyanweisungen enthalten.  
  
 Im folgenden Beispiel wird C3011 generiert:  
  
```  
// C3011.cpp // compile with: /openmp // processor: /x86 int main() { int   n = 0; #pragma omp parallel { _asm mov eax, n   // Delete this line to resolve this error. }   // C3011 }  
```