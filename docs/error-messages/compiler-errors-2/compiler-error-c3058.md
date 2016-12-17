---
title: "Compilerfehler C3058"
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
  - "C3058"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3058"
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3058
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbol": Das Symbol kann erst als "threadprivate" deklariert werden, wenn es in der copyin\-Klausel verwendet wird.  
  
 Ein Symbol muss zunächst als [threadprivate](../../parallel/openmp/reference/threadprivate.md) deklariert werden, bevor es in einer [copyin](../../parallel/openmp/reference/copyin.md)\-Klausel verwendet werden kann.  
  
 Im folgenden Beispiel wird C3058 generiert:  
  
```  
// C3058.cpp // compile with: /openmp int x, y, z; #pragma omp threadprivate(x, z) void test() { #pragma omp parallel copyin(x, y)   // C3058 { } }  
```  
  
 Mögliche Lösung:  
  
```  
// C3058b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { } }  
```