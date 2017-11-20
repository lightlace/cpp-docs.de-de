---
title: Compilerfehler C3007 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3007
dev_langs:
- C++
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4c8bb7b96f1ef86b4b667c0f8566d893e695f1cc
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3007"></a>Compilerfehler C3007
'Arg': Die Klausel für die 'Direktive'-Direktive von OpenMP nimmt kein Argument an.  
  
 Eine OpenMP-Direktive hat ein Argument aufgewiesen, aber die Direktive nimmt kein Argument an.  
  
 Im folgenden Beispiel wird C3007 generiert:  
  
```  
// C3007.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel for ordered(2)   // C3007  
}  
```