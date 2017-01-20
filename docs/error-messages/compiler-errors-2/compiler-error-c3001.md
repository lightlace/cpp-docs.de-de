---
title: "Compilerfehler C3001"
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
  - "C3001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3001"
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Fehler\_Text": Es wurde ein OpenMP\-Direktivenname erwartet.  
  
 \#pragma `omp` muss eine Direktive folgen.  
  
 Im folgenden Beispiel wird C3001 generiert:  
  
```  
// C3001.c // compile with: /openmp int main() { #pragma omp   // C3001 missing token }  
```