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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f0fe35a4021cca6ac1e3dd9846a3c165f50797f4
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3042"></a>Compilerfehler C3042
copyprivate- und nowait-Klauseln dürfen nicht zusammen in der 'Direktive'-Direktive von OpenMP vorkommen.  
  
 Die [copyprivate](../../parallel/openmp/reference/copyprivate.md) - und [nowait](../../parallel/openmp/reference/nowait.md) -Klauseln schließen sich in der angegebenen Richtung gegenseitig aus. Entfernen Sie eine oder beide der `copyprivate` - oder `nowait` -Klauseln.  
  
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
