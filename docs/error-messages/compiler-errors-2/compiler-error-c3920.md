---
title: Compilerfehler C3920 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3920
dev_langs: C++
helpviewer_keywords: C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5eeee973258b6d59b7a034e2b71bc453ed7454f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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