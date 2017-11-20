---
title: Compilerfehler C3766 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3766
dev_langs:
- C++
helpviewer_keywords:
- C3766
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f6df0cd4fea3f1f4b4e5e744b210fcc62bfff5f5
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3766"></a>Compilerfehler C3766
"Type" muss eine Implementierung für die Schnittstelle, Methode "Function" bereitstellen  
  
 Eine Klasse, die von einer Schnittstelle erbt, muss die Schnittstellenmember implementieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3766 generiert.  
  
```  
// C3766.cpp  
// compile with: /clr /c  
  
delegate void MyDel();  
  
interface struct IFace {  
   virtual event MyDel ^ E;  
};  
  
ref struct Class1 : public IFace {};   // C3766  
  
// OK  
ref struct Class2 : public IFace {  
   virtual event MyDel ^ E {  
      void add(MyDel ^) {}  
      void remove(MyDel ^) {}  
   }  
};  
```