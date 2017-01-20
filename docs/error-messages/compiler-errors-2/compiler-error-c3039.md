---
title: "Compilerfehler C3039"
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
  - "C3039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3039"
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": Die Indexvariable in der For\-Anweisung von OpenMP kann keine reduction\-Variable sein.  
  
 Da eine Indexvariable implizit privat ist, kann die Variable nicht in einer [reduction](../../parallel/openmp/reference/reduction.md)\-Klausel in der einschließenden [parallel](../../parallel/openmp/reference/parallel.md)\-Direktive verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3039 generiert:  
  
```  
// C3039.cpp // compile with: /openmp /c int g_i; int main() { int i; #pragma omp parallel reduction(+: i) { #pragma omp for for (i = 0; i < 10; ++i)   // C3039 g_i += i; } }  
```