---
title: "Compilerfehler C3032"
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
  - "C3032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3032"
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": Die Variable in der Klausel\-Klausel kann keinen unvollständigen Typ "Typ" aufweisen.  
  
 Typen, die an bestimmte Klauseln übergeben werden, müssen für den Compiler vollständig sichtbar sein.  
  
 Im folgenden Beispiel wird C3032 generiert:  
  
```  
// C3032.cpp // compile with: /openmp /link vcomps.lib #include "omp.h" struct Incomplete; extern struct Incomplete inc; int main() { int i = 9; #pragma omp parallel private(inc)   // C3032 ; #pragma omp parallel private(i)     // OK ; }  
```