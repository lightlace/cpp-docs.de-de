---
title: "Compilerfehler C3023"
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
  - "C3023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3023"
ms.assetid: 89dcce98-3cd7-4931-a50f-87df1d2ebc9b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Wert": Im Argument für die "Klausel"\-Klausel von OpenMP wurde ein unerwartetes Token gefunden.  
  
 Die an eine Klausel übergebenen Werte waren nicht gültig.  
  
 Im folgenden Beispiel wird C3023 generiert:  
  
```  
// C3023.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" int main() { int i; #pragma omp parallel for schedule(dynamic 10)   // C3023 for (i = 0; i < 10; ++i) ; #pragma omp parallel for schedule(dynamic;10)   // C3023 for (i = 0; i < 10; ++i) ; // OK #pragma omp parallel for schedule(dynamic, 10) for (i = 0; i < 10; ++i) ; }  
```