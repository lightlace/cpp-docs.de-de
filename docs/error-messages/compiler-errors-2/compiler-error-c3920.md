---
title: Compilerfehler C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: e3c37cba4b7df2df9e9784b3a1afb8dbf9c8e8d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491727"
---
# <a name="compiler-error-c3920"></a>Compilerfehler C3920

' Operator'': kann nicht definiert, eine Postfix-Inkrement/Dekrement WinRT oder CLR-Operator Aufrufen des Postfix WinRT oder CLR-Operator Ruft das entsprechende Präfix WinRT oder CLR-Operator (Op_Increment/op_Decrement) aufgerufen, jedoch mit Postfix-Semantik

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