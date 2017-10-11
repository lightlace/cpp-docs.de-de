---
title: Compilerfehler C3210 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3210
dev_langs:
- C++
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f4825abf58b7c0277b3e7f00ce16bcd0d5b1df64
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3210"></a>Compilerfehler C3210
'Typ': Zugriffsdeklaration kann nur auf einen Member der Basisklasse angewendet werden  
  
 Ein [using-Deklaration](../../cpp/using-declaration.md) wurde falsch angegeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3210 generiert.  
  
```  
// C3210.cpp  
// compile with: /c  
struct A {  
protected:  
   int i;  
};  
  
struct B {  
   using A::i;   // C3210  
};  
  
struct C : public A {  
   using A::i;   // OK  
};  
```
