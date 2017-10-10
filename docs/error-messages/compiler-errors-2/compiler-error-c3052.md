---
title: Compilerfehler C3052 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3052
dev_langs:
- C++
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 59686a585f66092fbf059cc5e84f7da493134b7f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3052"></a>Compilerfehler C3052
"Var": Die Variable wird in einer Datenfreigabeklausel nicht unter einer default(none)-Klausel angezeigt.  
  
 Wenn [default(none)](../../parallel/openmp/reference/default-openmp.md) verwendet wird, muss jede in einem strukturierten Block verwendete Variable explizit als [shared](../../parallel/openmp/reference/shared-openmp.md) oder [private](../../parallel/openmp/reference/private-openmp.md)angegeben werden.  
  
 Im folgenden Beispiel wird C3052 generiert.  
  
```  
// C3052.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(none) // shared(n1) private(n1)  
   {  
      n1 = 0;   // C3052 use either a shared or private clause  
   }  
}  
```
