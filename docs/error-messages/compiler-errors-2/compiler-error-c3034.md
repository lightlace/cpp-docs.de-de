---
title: "Compilerfehler C3034"
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
  - "C3034"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3034"
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3034
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OpenMP directive1\-Direktive von kann nicht direkt in der directive1\-Direktive geschachtelt werden.  
  
 Bestimmte Direktiven können nicht geschachtelt werden. Um diesen Fehler zu beheben, können Sie die Anweisungen der beiden Direktiven in den Block einer Direktive zusammenführen, oder Sie können aufeinander folgende Direktiven erstellen.  
  
 Im folgenden Beispiel wird C3034 generiert:  
  
```  
// C3034.cpp // compile with: /openmp /link vcomps.lib int main() { #pragma omp single { #pragma omp single   // C3034 { ; } } // Two consecutive single clauses are OK. #pragma omp single { } #pragma omp single { } }  
```