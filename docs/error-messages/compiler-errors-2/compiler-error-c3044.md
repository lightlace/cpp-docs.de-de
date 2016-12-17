---
title: "Compilerfehler C3044"
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
  - "C3044"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3044"
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3044
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

section: Nur bei direkter Schachtelung unter einer sections\-Direktive von OpenMP zulässig.  
  
 Der Compiler hat herausgefunden, dass eine `section`\-Direktive falsch verwendet wurde. Weitere Informationen finden Sie unter [sections](../../parallel/openmp/reference/sections-openmp.md).  
  
 Im folgenden Beispiel wird C3044 generiert:  
  
```  
// C3044.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { ++n2; } #pragma omp section   // C3044 { ++n3; } } #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section   // OK { ++n3; } } } }  
```