---
title: "Compilerfehler C3055"
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
  - "C3055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3055"
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Auf das Symbol kann erst verwiesen werden, wenn es in der threadprivate\-Direktive verwendet wird.  
  
 Es wurde auf ein Symbol verwiesen und dieses dann in einer [threadprivate](../../parallel/openmp/reference/threadprivate.md)\-Klausel verwendet. Dies ist nicht zulässig.  
  
 Im folgenden Beispiel wird C3055 generiert:  
  
```  
// C3055.cpp // compile with: /openmp int x, y; int z = x; #pragma omp threadprivate(x, y)   // C3055 void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 Mögliche Lösung:  
  
```  
// C3055b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```