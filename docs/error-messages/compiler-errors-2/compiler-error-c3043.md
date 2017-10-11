---
title: Compilerfehler C3043 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3043
dev_langs:
- C++
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2ec3f70fa176b8562067985b5b2d48ee2aa39b8e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3043"></a>Compilerfehler C3043
Die critical-Direktive von OpenMP kann nicht in einer critical-Direktive mit dem gleichen Namen geschachtelt werden.  
  
 Die [critical](../../parallel/openmp/reference/critical.md) -Direktive kann nicht in einer `critical` -Direktive mit dem gleichen Namen geschachtelt werden.  
  
 Im folgenden Beispiel wird C3043 generiert:  
  
```  
// C3043.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n1 = 1, n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp critical(MyTest)  
      {  
         ++n2;  
  
         #pragma omp critical(MyTest)   // C3043  
         // try the following line instead  
         // #pragma omp critical(MyTest2)  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```
