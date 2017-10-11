---
title: Compilerfehler C3655 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3655
dev_langs:
- C++
helpviewer_keywords:
- C3655
ms.assetid: 724919ab-2915-4b61-8794-44648e162d62
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6ac13086c64887a916041853db7606aa2e1e532
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3655"></a>Compilerfehler C3655
'Funktion': Funktion wurde bereits explizit überschrieben.  
  
 Eine Funktion kann nur explizit einmal überschrieben werden. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3655 generiert:  
  
```  
// C3655.cpp  
// compile with: /clr /c  
public ref struct B {  
   virtual void f();  
   virtual void g();  
};  
  
public ref struct D : B {  
   virtual void f() new sealed = B::f;  
   virtual void g() new sealed = B::f;   // C3655  
   // try the following line instead  
   // virtual void g() new sealed = B::g;  
};  
```
