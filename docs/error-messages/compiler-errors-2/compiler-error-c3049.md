---
title: "Compilerfehler C3049"
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
  - "C3049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3049"
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Arg": Ungültiges Argument in der "default"\-Klausel von OpenMP  
  
 Es wurde ein falscher Wert an eine [default](../../parallel/openmp/reference/default-openmp.md)\-Klausel übergeben.  
  
 Im folgenden Beispiel wird C3049 generiert:  
  
```  
// C3049.cpp // compile with: /openmp /c int main() { int n1 = 1; #pragma omp parallel default(private)   // C3049 // try the following line instead // #pragma omp parallel default(shared) { ++n1; } }  
```