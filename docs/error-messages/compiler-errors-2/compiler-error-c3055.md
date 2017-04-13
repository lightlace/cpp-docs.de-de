---
title: Compilerfehler C3055 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3055
dev_langs:
- C++
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f5c657322e901da8658e5d7d99e3d28c3392b579
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3055"></a>Compilerfehler C3055
'Symbol': Auf das Symbol kann erst verwiesen werden, wenn es in der threadprivate-Direktive verwendet wird.  
  
 Ein Symbol wurde auf die verwiesen wird, und klicken Sie dann verwendet eine [Threadprivate](../../parallel/openmp/reference/threadprivate.md) -Klausel, was nicht zulässig ist.  
  
 Im folgenden Beispiel wird C3055 generiert:  
  
```  
// C3055.cpp  
// compile with: /openmp  
int x, y;  
int z = x;  
#pragma omp threadprivate(x, y)   // C3055  
  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C3055b.cpp  
// compile with: /openmp /LD  
int x, y, z;  
#pragma omp threadprivate(x, y)  
  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```
