---
title: "Compilerfehler C3042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3042"
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

copyprivate\- und nowait\-Klauseln dürfen nicht zusammen in der 'Direktive'\-Direktive von OpenMP vorkommen.  
  
 Die [copyprivate](../../parallel/openmp/reference/copyprivate.md)\- und [nowait](../../parallel/openmp/reference/nowait.md)\-Klauseln schließen sich in der angegebenen Richtung gegenseitig aus. Entfernen Sie eine oder beide der `copyprivate`\- oder `nowait`\-Klauseln.  
  
 Im folgenden Beispiel wird C3042 generiert.  
  
```  
// C3042.cpp // compile with: /openmp /c #include <stdio.h> #include "omp.h" double d; int main() { #pragma omp parallel private(d) { #pragma omp single copyprivate(d) nowait   // C3042 { } } }  
```