---
title: Compilerfehler C2325 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2325
dev_langs:
- C++
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9fd84bb01f23b077030174d8c5bc5bf6b1c3f21e
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2325"></a>Compilerfehler C2325
"Typ": Unerwarteter Typ auf der rechten Seite des "Name"  
  
 Erfolgt ein Aufruf von einem Destruktor mit falschen Typ.  
  
 Im folgende Beispiel wird C2325 generiert:  
  
```  
// C2325.cpp  
// compile with: /c  
class A {};  
typedef A* pA_t;  
void f() {  
    A** ppa = new A *;  
    ppa->~A*;   // C2325  
  
   pA_t *ppa2 = new pA_t;  
   ppa2->~pA_t();   // OK  
}  
```