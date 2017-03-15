---
title: "Compilerfehler C3059 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3059"
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Var": Ein threadprivate\-Symbol kann nicht in der \<Klausel\>\-Klausel verwendet werden.  
  
 Ein [threadprivate](../../parallel/openmp/reference/threadprivate.md) Symbol wurde in einer Klausel verwendet.  
  
 Im folgenden Beispiel wird C3059 generiert.  
  
```  
// C3059.cpp // compile with: /openmp #include "omp.h" int x, y; #pragma omp threadprivate(x, y) int main() { #pragma omp parallel private(x, y)   // C3059 { x = y; } }  
```  
  
 Mögliche Lösung:  
  
```  
// C3059b.cpp // compile with: /openmp #include "omp.h" int x = 0, y = 0; int main() { #pragma omp parallel firstprivate(y) private(x) { x = y; } }  
```