---
title: "Compilerfehler C3037"
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
  - "C3037"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3037"
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3037
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": Variable in reduction\-Klausel muss im übergeordneten Kontext freigegeben sein.  
  
 Eine in einer [reduction](../../parallel/openmp/reference/reduction.md)\-Klausel angegebene Variable darf nicht für jeden Thread im Kontext privat sein.  
  
 Im folgenden Beispiel wird C3037 generiert:  
  
```  
// C3037.cpp // compile with: /openmp /c int g_i; int main() { int i; #pragma omp parallel private(g_i) // try the following line instead // #pragma omp parallel { #pragma omp for reduction(+:g_i)   // C3037 for (i = 0 ; i < 10 ; ++i) { g_i += i; } } }  
```