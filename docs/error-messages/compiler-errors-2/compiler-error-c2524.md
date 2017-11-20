---
title: Compilerfehler C2524 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2524
dev_langs:
- C++
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f0b80ac9029f530b68afdc379d7660bba1ff76cb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2524"></a>Compilerfehler C2524
'Destruktor': ein Destruktor/Finalizer muss eine "void"-Parameterliste haben  
  
 Der Destruktor oder Finalizer hat eine Parameterliste, die nicht ["void"](../../cpp/void-cpp.md). Andere Parametertypen sind nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird C2524 generiert.  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird C2524 generiert.  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```