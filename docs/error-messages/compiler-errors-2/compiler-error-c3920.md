---
title: "Compilerfehler C3920"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3920"
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Operator": kann keinen Postfix\-Inkrement\/Dekrement WinRT oder CLR\-Operator definieren. Aufrufen des Postfix WinRT oder CLR\-Operators wird das entsprechende Präfix WinRT oder CLR\-Operator \(Op\_Increment\/op\_Decrement\) aufrufen, jedoch mit Postfix\-Semantik.  
  
 Windows\-Runtime und CLR unterstützen den Postfixoperator nicht und benutzerdefinierte Postfix\-Operatoren sind nicht zulässig.  Sie können einen Präfixoperator definieren und der Präfixoperator wird für Vor\- und Postinkrement\-Operationen verwendet.  
  
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