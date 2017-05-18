---
title: Compilerfehler C3042 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3042
dev_langs:
- C++
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d6e26077e9ced646615681c1472661145939887a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3042"></a>Compilerfehler C3042
copyprivate- und nowait-Klauseln dürfen nicht zusammen in der 'Direktive'-Direktive von OpenMP vorkommen.  
  
 Die [Copyprivate](../../parallel/openmp/reference/copyprivate.md) und [Nowait](../../parallel/openmp/reference/nowait.md) Klauseln sind in der angegebenen gegenseitig. Entfernen Sie eine oder beide der `copyprivate` - oder `nowait` -Klauseln.  
  
 Im folgenden Beispiel wird C3042 generiert.  
  
```  
// C3042.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
#include "omp.h"  
  
double d;  
  
int main() {  
    #pragma omp parallel private(d)  
   {  
      #pragma omp single copyprivate(d) nowait   // C3042  
      {  
      }  
   }  
}  
```
