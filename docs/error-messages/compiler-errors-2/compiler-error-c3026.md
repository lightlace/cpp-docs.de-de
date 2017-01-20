---
title: "Compilerfehler C3026"
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
  - "C3026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3026"
ms.assetid: 3297060e-cc5b-4600-a2db-09bfc4ffa21f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klausel": konstanter Ausdruck muss positiv sein.  
  
 Einer Klausel wurde ein ganzzahliger Wert übergeben, der jedoch keine positive Zahl war. Die Zahl muss positiv sein.  
  
## Beispiel  
 Im folgenden Beispiel wird C3026 generiert:  
  
```  
// C3026.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" int main() { int i; const int i1 = 0; #pragma omp parallel for num_threads(i1)   // C3026 for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); #pragma omp parallel for num_threads(i1 + 1)   // OK for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); }  
```