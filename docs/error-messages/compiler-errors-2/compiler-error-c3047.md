---
title: Compilerfehler C3047 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3047
dev_langs: C++
helpviewer_keywords: C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46965c20dd38e7cab8014998237ad0e32bda6d99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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