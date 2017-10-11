---
title: Compilerfehler C3920 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2e2bf82de4e32c2b0ae586c78c69ce474947c3ec
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3920"></a>Compilerfehler C3920
"Operator": kann nicht definiert, ein Postfix-Inkrement/Dekrement WinRT oder CLR-Operator Aufrufen des Postfix WinRT oder CLR-Operator Ruft das entsprechende Präfix WinRT oder CLR-Operator (Op_Increment/Op_Decrement), jedoch mit Postfix-Semantik  
  
 Windows-Runtime und CLR unterstützen den Postfixoperator nicht und benutzerdefinierte Postfix-Operatoren sind nicht zulässig.  Sie können einen Präfixoperator definieren und der Präfixoperator wird für Vor- und Postinkrement-Operationen verwendet.  
  
 Im folgenden Beispiel wird C3920 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```
