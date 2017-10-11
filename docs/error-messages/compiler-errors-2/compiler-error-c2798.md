---
title: Compiler-Fehler C2798 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bb0a411651cf7c7f614942563baee5f04075fdf3
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2798"></a>Compiler-Fehler C2798 generiert
'Super:: Member' ist mehrdeutig  
  
 Mehrere geerbte Strukturen enthalten, das Element, das Sie auf die verwiesen wird mit [super](../../cpp/super.md). Sie können entweder durch den Fehler beheben:  
  
-   Entfernen von B1 oder B2 aus der Vererbungsliste von D.  
  
-   Ändern des Namens des Datenmembers in B1 oder B2.  
  
 Im folgende Beispiel wird C2798 generiert:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```
