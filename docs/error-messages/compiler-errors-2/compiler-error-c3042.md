---
title: "Compilerfehler C3042"
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
  - "C3042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3042"
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

copyprivate\- und nowait\-Klauseln dürfen nicht zusammen in der 'Direktive'\-Direktive von OpenMP vorkommen.  
  
 Die [copyprivate](../../parallel/openmp/reference/copyprivate.md)\- und [nowait](../../parallel/openmp/reference/nowait.md)\-Klauseln schließen sich in der angegebenen Richtung gegenseitig aus. Entfernen Sie eine oder beide der `copyprivate`\- oder `nowait`\-Klauseln.  
  
 Im folgenden Beispiel wird C3042 generiert.  
  
```  
// C3042.cpp // compile with: /openmp /c #include <stdio.h> #include "omp.h" double d; int main() { #pragma omp parallel private(d) { #pragma omp single copyprivate(d) nowait   // C3042 { } } }  
```