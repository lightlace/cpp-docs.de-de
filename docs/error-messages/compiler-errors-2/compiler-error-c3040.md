---
title: "Compilerfehler C3040 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3040"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3040"
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3040
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Var': Der Typ der Variable in der reduction\-Klausel ist nicht kompatibel mit dem reduction\-Operator 'Operator'.  
  
 Eine Variable in einer [reduction](../../parallel/openmp/reference/reduction.md)\-Klausel kann nicht mit dem reduction\-Operator verwendet werden.  
  
 Im folgenden Beispiel wird C3040 generiert:  
  
```  
// C3040.cpp // compile with: /openmp /c #include "omp.h" double d; int main() { #pragma omp parallel reduction(&:d)   // C3040 ; #pragma omp parallel reduction(-:d)  // OK ; }  
```