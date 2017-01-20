---
title: "Compilerfehler C3041"
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
  - "C3041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3041"
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": Die Variable in der copyprivate\-Klausel muss im umschließenden Kontext privat sein  
  
 Eine an [copyprivate](../../parallel/openmp/reference/copyprivate.md) übergebene Variable kann im umschließenden Kontext nicht freigegeben werden.  
  
 Im folgenden Beispiel wird C3041 generiert.  
  
```  
// C3041.cpp // compile with: /openmp /c #include "omp.h" double d; int main() { #pragma omp parallel shared(d) // try the following line instead // #pragma omp parallel private(d) { // or don't make d copyprivate #pragma omp single copyprivate(d)   // C3041 { } } }  
```