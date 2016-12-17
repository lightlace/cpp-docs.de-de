---
title: "Compilerfehler C3056"
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
  - "C3056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3056"
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': Das Symbol befindet sich nicht im gleichen Bereich wie die 'threadprivate'\-Direktive.  
  
 Ein in einer [threadprivate](../../parallel/openmp/reference/threadprivate.md)\-Klausel verwendetes Symbol muss sich im gleichen Bereich wie die `threadprivate`\-Klausel befinden.  
  
 Im folgenden Beispiel wird C3056 generiert:  
  
```  
// C3056.cpp // compile with: /openmp int x, y; void test() { #pragma omp threadprivate(x, y)   // C3056 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 Mögliche Lösung:  
  
```  
// C3056b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```