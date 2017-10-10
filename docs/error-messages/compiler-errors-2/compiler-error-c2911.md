---
title: Compilerfehler C2911 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2911
dev_langs:
- C++
helpviewer_keywords:
- C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a3f37aae72a38ecdf89da2a47683cc6e1c8f3ea9
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2911"></a>Compilerfehler C2911
"Member": Kann nicht im aktuellen Bereich deklariert oder definiert werden.  
  
 In einem Namespace, einer Klasse oder einer Funktion können Sie nur einen Member desselben Namespace, derselben Klasse oder derselben Funktion oder einen Member definieren, der vom selben Namespace, derselben Klasse oder derselben Funktion umschlossen ist.  
  
 Im folgenden Beispiel wird C2911 generiert:  
  
```  
// C2911.cpp  
struct A;  
  
namespace M {  
   struct D;  
}  
  
namespace N {  
   struct C;  
  
   namespace O {  
      struct B;  
   }  
  
   // in N  
   struct ::A {};   // C2911  A is member of global NS  
   struct O::B{};   // OK B is in O, O is inside of N  
   struct C {};     // OK C is member of N  
   struct M::D {};  // C2911 D is member of M, M not enclosed by N  
}  
```
