---
title: Compilerfehler C3038 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3038
dev_langs:
- C++
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
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
ms.openlocfilehash: 32a63dcc218d7319b74a4b6941b2b25d6910e4a5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3038"></a>Compilerfehler C3038
"Var": Die Variable in der private-Klausel kann im umschließenden Kontext keine reduction-Variable sein.  
  
 Variablen in der [Verringerung](../../parallel/openmp/reference/reduction.md) -Klausel einer parallel-Anweisung kann nicht angegeben werden, einem [private](../../parallel/openmp/reference/private-openmp.md) -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden.  
  
 Im folgenden Beispiel wird C3038 generiert.  
  
```  
// C3038.cpp  
// compile with: /openmp /c  
int g_i, g_i2;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: g_i)  
   {  
      #pragma omp for private(g_i)   // C3038  
      // try the following line instead  
      // #pragma omp for private(g_i2)  
      for (i = 0; i < 10; ++i)  
         g_i += i;  
   }  
}  
```
