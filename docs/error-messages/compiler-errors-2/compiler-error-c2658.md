---
title: Compiler-Fehler C2658 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 252c543b8ba4dfc470bc1641a3d91c3dfc06177d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2658"></a>Compiler-Fehler C2658 generiert
'Member': Neudefinition in einer anonymen Struktur/Union  
  
 Zwei anonyme Strukturen oder Unions enthalten Memberdeklarationen mit dem gleichen Bezeichner jedoch mit unterschiedlichen Typen auf. Klicken Sie unter ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md), Sie erhalten diesen Fehler auch für Member mit dem gleichen Bezeichner und Typ.  
  
 Im folgende Beispiel wird C2658 generiert:  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```
