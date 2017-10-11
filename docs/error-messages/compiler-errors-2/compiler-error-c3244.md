---
title: Compilerfehler C3244 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3244
dev_langs:
- C++
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 225b3e95e2f0ba7e41959732f2c11b8860ef8b3b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3244"></a>Compilerfehler C3244
'methode': Diese Methode wurde von 'schnittstelle' eingeführt, nicht von 'schnittstelle'  
  
 Versuch zum [expliziten Überschreiben](../../cpp/explicit-overrides-cpp.md) eines Members, der in der angegebenen Schnittstelle nicht vorhanden ist, wohl aber in einer anderen Basisklasse.  
  
 Im folgenden Beispiel wird C3244 generiert:  
  
```  
// C3244.cpp  
#pragma warning(disable:4199)  
  
__interface IX15A {  
   void f();  
};  
  
__interface IX15B {  
   void g();  
};  
  
class CX15 : public IX15A, public IX15B {  
public:        
   void IX15A::f();  
   void IX15B::g();  
};  
  
void CX15::IX15A::g()   // C3244 occurs here  
{  
}  
```
