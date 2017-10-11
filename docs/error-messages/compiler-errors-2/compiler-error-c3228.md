---
title: Compilerfehler C3228 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3228
dev_langs:
- C++
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1176da0e3c2583d5a48d78a9f2689d5cf0bc40be
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3228"></a>Compilerfehler C3228
'function': Das generische Typargument für 'param' kann nicht 'typ' sein, es muss ein Werttyp oder ein Handletyp sein  
  
 Ein falscher Typ wurde als generisches Typargument übergeben.  
  
 Im folgenden Beispiel wird C3228 generiert:  
  
```  
// C3228.cpp  
// compile with: /clr  
class A {};  
  
value class B {};  
  
generic <class T>  
void Test() {}  
  
ref class C {  
public:  
   generic <class T>  
   static void f() {}  
};  
  
int main() {  
   C::f<A>();   // C3228  
   C::f<B>();   // OK  
  
   Test<C>();   // C3228  
   Test<C ^>();   // OK  
}  
```
