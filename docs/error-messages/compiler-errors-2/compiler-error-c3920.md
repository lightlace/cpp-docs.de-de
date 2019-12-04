---
title: Compilerfehler C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: 416752054f7397a058329e1ee4bdaef693dd0d28
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758462"
---
# <a name="compiler-error-c3920"></a>Compilerfehler C3920

' Operator ' ': ein postfix-Inkrement/Dekrement-WinRT-oder CLR-Operator, der den Postfix WinRT-oder CLR-Operator aufruft, kann nicht definiert werden, ruft das entsprechende Präfix WinRT oder CLR-Operator (op_Increment/op_Decrement), jedoch mit Postfix-Semantik

Windows-Runtime und CLR unterstützen den Postfixoperator nicht und benutzerdefinierte Postfix-Operatoren sind nicht zulässig.  Sie können einen Präfixoperator definieren und der Präfixoperator wird für Vor- und Postinkrement-Operationen verwendet.

Im folgenden Beispiel wird C3920 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
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
