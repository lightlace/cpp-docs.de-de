---
title: Compilerfehler C3035 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3035
dev_langs:
- C++
helpviewer_keywords:
- C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 820a09741508c710d851182d9e1a02489c1ed2ac
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3035"></a>Compilerfehler C3035
Die ordered-Direktive von OpenMP muss mit der ordered-Klausel direkt an eine For-Direktive oder eine Parallel For-Direktive gebunden werden.  
  
 Eine ordered-Klausel weist ein nicht ordnungsgemäßes Format auf.  
  
 Im folgenden Beispiel wird C3035 generiert:  
  
```  
// C3035.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   int n = 0, x, i;  
  
   #pragma omp parallel private(n)  
   {  
      #pragma omp ordered   // C3035  
      // Try the following line instead:  
      // #pragma omp for ordered  
       for (i = 0 ; i < 10 ; ++i)  
         ;  
   }  
}  
```
