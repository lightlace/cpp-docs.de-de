---
title: "Compilerfehler C3048"
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
  - "C3048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3048"
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Ausdruck, der auf "\#pragma omp atomic" folgt, weist eine ungültige Form auf.  
  
 Eine atomic\-Direktive wurde falsch angegeben.  
  
 Im folgenden Beispiel wird C3048 generiert.  
  
```  
// C3048.cpp // compile with: /openmp vcomps.lib #include "omp.h" #include <stdio.h> int main() { int a[10]; omp_set_num_threads(4); #pragma omp parallel { #pragma omp atomic a[0] = 1;   // C3048 // try the following line instead // a[0] += 1; } }  
```