---
title: Compilerfehler C3890 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3890
dev_langs:
- C++
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3f98846bc8a361bd03d453f2115e2063f37423f0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3890"></a>Compilerfehler C3890
"Var": Sie können die Adresse von einem literal-Datenmember nicht übernehmen  
  
 Ein literal-Datenmember ist auf dem Heap der Garbage collection vorhanden.  Ein Objekt auf dem Heap der Garbage collection kann verschoben werden, damit die Übernahme der Adresse nicht sinnvoll ist.  
  
 Im folgende Beispiel wird C3890 generiert:  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```
