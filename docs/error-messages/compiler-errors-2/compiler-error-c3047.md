---
title: "Compilerfehler C3047"
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
  - "C3047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3047"
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vor einem strukturierten Block in einem sections\-Bereich von OpenMP muss sich "\#pragma omp section" befinden.  
  
 Jeglicher Code in einem Codeblock, der durch eine [sections](../../parallel/openmp/reference/sections-openmp.md)\-Direktive eingeführt wird, muss sich in einem Codeblock befinden, der durch eine `section`\-Direktive eingeführt wird.  
  
 Im folgenden Beispiel wird C3047 generiert:  
  
```  
// C3047.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section { ++n3; } ++n2;   // C3047 not enclosed in #pragma omp section } } }  
```