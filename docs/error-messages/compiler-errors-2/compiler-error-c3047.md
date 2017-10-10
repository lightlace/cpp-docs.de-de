---
title: Compilerfehler C3047 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3047
dev_langs:
- C++
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5d2133330ab45eb4667c100cde9495e54eec15e7
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3047"></a>Compilerfehler C3047
Vor einem strukturierten Block in einem sections-Bereich von OpenMP muss sich "#pragma omp section" befinden.  
  
 Jeglicher Code in einem Codeblock, der durch eine [sections](../../parallel/openmp/reference/sections-openmp.md) -Direktive eingeführt wird, muss sich in einem Codeblock befinden, der durch eine `section` -Direktive eingeführt wird.  
  
 Im folgenden Beispiel wird C3047 generiert:  
  
```  
// C3047.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
  
         #pragma omp section  
         {  
            ++n3;  
         }  
  
         ++n2;   // C3047 not enclosed in #pragma omp section  
      }  
   }  
}  
```
