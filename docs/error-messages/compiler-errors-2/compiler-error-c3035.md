---
title: "Compilerfehler C3035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3035"
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die ordered\-Direktive von OpenMP muss mit der ordered\-Klausel direkt an eine For\-Direktive oder eine Parallel For\-Direktive gebunden werden.  
  
 Eine ordered\-Klausel weist ein nicht ordnungsgemäßes Format auf.  
  
 Im folgenden Beispiel wird C3035 generiert:  
  
```  
// C3035.cpp // compile with: /openmp /link vcomps.lib int main() { int n = 0, x, i; #pragma omp parallel private(n) { #pragma omp ordered   // C3035 // Try the following line instead: // #pragma omp for ordered for (i = 0 ; i < 10 ; ++i) ; } }  
```