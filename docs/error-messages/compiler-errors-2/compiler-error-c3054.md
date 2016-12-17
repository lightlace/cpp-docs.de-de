---
title: "Compilerfehler C3054"
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
  - "C3054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3054"
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\#pragma omp parallel" wird in einer generischen Klasse oder Funktion derzeit nicht unterstützt.  
  
 Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md) und [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3054 generiert.  
  
```  
// C3054.cpp // compile with: /openmp /clr /c #include <omp.h> ref struct MyBaseClass { // Delete the following 7 lines to resolve. generic <class ItemType> void Test(ItemType i) {   // C3054 #pragma omp parallel num_threads(4) { int i = omp_get_thread_num(); } } // OK void Test2() { #pragma omp parallel num_threads(4) { int i = omp_get_thread_num(); } } };  
```