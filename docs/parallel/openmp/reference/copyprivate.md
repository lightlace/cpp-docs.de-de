---
title: "copyprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "copyprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copyprivate OpenMP clause"
ms.assetid: 02c0209d-abe8-4797-8365-a82b53c3f15d
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# copyprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass eine oder mehrere Variablen mit allen Threads freigegeben werden sollen.  
  
## Syntax  
  
```  
copyprivate(var)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var`  
 Eine oder mehrere Variablen freizugeben.  Wenn mehrere Variablen angegeben wird, trennen Sie die Variablennamen durch Kommas.  
  
## Hinweise  
 `copyprivate` gilt für [single](../../../parallel/openmp/reference/single.md) die Direktive.  
  
 Weitere Informationen finden Sie unter [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md).  
  
## Beispiel  
  
```  
// omp_copyprivate.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
float x, y, fGlobal = 1.0;  
#pragma omp threadprivate(x, y)  
  
float get_float() {  
   fGlobal += 0.001;  
   return fGlobal;  
}  
  
void use_float(float f, int t) {  
   printf_s("Value = %f, thread = %d\n", f, t);  
}  
  
void CopyPrivate(float a, float b) {  
   #pragma omp single copyprivate(a, b, x, y)   
   {  
      a = get_float();  
      b = get_float();  
      x = get_float();  
      y = get_float();  
    }  
  
   use_float(a, omp_get_thread_num());     
   use_float(b, omp_get_thread_num());     
   use_float(x, omp_get_thread_num());  
   use_float(y, omp_get_thread_num());  
}  
  
int main() {  
   float a = 9.99, b = 123.456;  
  
   printf_s("call CopyPrivate from a single thread\n");  
   CopyPrivate(9.99, 123.456);  
  
   printf_s("call CopyPrivate from a parallel region\n");  
   #pragma omp parallel       
   {  
      CopyPrivate(a, b);  
   }  
}  
```  
  
  **CopyPrivate Aufruf von einem einzigen Thread**  
**Wert \= 1.001000, Thread \= 0**  
**Wert \= 1.002000, Thread \= 0**  
**Wert \= 1.003000, Thread \= 0**  
**Wert \= 1.004000, Thread \= 0**  
**CopyPrivate Aufruf von einem parallelen Bereich**  
**Wert \= 1.005000, Thread \= 0**  
**Wert \= 1.005000, Thread \= 1**  
**Wert \= 1.006000, Thread \= 0**  
**Wert \= 1.006000, Thread \= 1**  
**Wert \= 1.007000, Thread \= 0**  
**Wert \= 1.007000, Thread \= 1**  
**Wert \= 1.008000, Thread \= 0**  
**Wert \= 1.008000, Thread \= 1**   
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)