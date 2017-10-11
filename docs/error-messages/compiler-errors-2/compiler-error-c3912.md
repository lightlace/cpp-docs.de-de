---
title: Compilerfehler C3912 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3912
dev_langs:
- C++
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5198258264688196a1ddc27059ab1f1349048c1
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3912"></a>Compilerfehler C3912
'Ereignis': Typ des Ereignisses muss ein Delegattyp sein  
  
 Ein Ereignis wurde deklariert, aber es war nicht mit dem richtigen Typ.  
  
 Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3912 generiert:  
  
```  
// C3912.cpp  
// compile with: /clr  
delegate void H();  
ref class X {  
   event int Ev;   // C3912  
   event H^ Ev2;   // OK  
};  
```
