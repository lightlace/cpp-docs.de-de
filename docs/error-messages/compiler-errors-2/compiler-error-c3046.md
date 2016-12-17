---
title: "Compilerfehler C3046"
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
  - "C3046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3046"
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlender strukturierter Block in einem \#pragma omp sections\-Bereich von OpenMP.  
  
 Eine [sections](../../parallel/openmp/reference/sections-openmp.md)\-Direktive weist einen leeren Codeblock auf.  
  
 Im folgenden Beispiel wird C3046 generiert:  
  
```  
// C3046.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { /* ++n2; #pragma omp section { ++n3; } */ }   // C3046 uncomment code to resolve this C3046 } }  
```