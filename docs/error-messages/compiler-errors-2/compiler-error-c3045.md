---
title: "Compilerfehler C3045 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3045"
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurde erwartet, dass auf die sections\-Direktive von OpenMP eine Verbundanweisung folgt. '{' fehlt  
  
 Ein durch geschweifte Klammern begrenzter Codeblock muss auf eine [sections](../../parallel/openmp/reference/sections-openmp.md)\-Direktive folgen.  
  
 Im folgenden Beispiel wird C3045 generiert:  
  
```  
// C3045.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections ++n2;   // C3045 #pragma omp sections   // OK { ++n3; } } }  
```