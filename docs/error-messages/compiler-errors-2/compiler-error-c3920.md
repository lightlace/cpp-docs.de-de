---
title: Compilerfehler C3920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ced0a0f8fa2b6694de4dd901d71f6721e12493b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270279"
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