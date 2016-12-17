---
title: "Compilerfehler C3030"
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
  - "C3030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3030"
ms.assetid: de92fd7e-29ba-46e8-b43b-f4b985cd74de
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Die Variable in der reduction\-Klausel\/\-Direktive kann keinen Verweistyp aufweisen  
  
 Bestimmten Klauseln, wie etwa der reduction\-Klausel, können nur Wertparameter übergeben werden.  
  
 Im folgenden Beispiel wird C3030 generiert:  
  
```  
// C3030.cpp // compile with: /openmp /link vcomps.lib #include "omp.h" void test(int &r) { #pragma omp parallel reduction(+ : r)   // C3030 ; } void test2(int r) { #pragma omp parallel reduction(+ : r)   // OK ; } int main(int argc, char** argv) { int& r = *((int*)argv); int s = *((int*)argv); #pragma omp parallel reduction(+ : r)   // C3030 ; #pragma omp parallel reduction(+ : s)   // OK ; }  
```