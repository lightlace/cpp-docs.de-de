---
title: "Compilerfehler C3043"
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
  - "C3043"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3043"
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3043
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die critical\-Direktive von OpenMP kann nicht in einer critical\-Direktive mit dem gleichen Namen geschachtelt werden.  
  
 Die [critical](../../parallel/openmp/reference/critical.md)\-Direktive kann nicht in einer `critical`\-Direktive mit dem gleichen Namen geschachtelt werden.  
  
 Im folgenden Beispiel wird C3043 generiert:  
  
```  
// C3043.cpp // compile with: /openmp /c #include "omp.h" int main() { int n1 = 1, n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp critical(MyTest) { ++n2; #pragma omp critical(MyTest)   // C3043 // try the following line instead // #pragma omp critical(MyTest2) { ++n3; } } } }  
```