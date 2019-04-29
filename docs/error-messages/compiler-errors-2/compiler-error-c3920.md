---
title: Compilerfehler C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: d7163cf07a440a0afd1216b3e5cf665326ffb963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386602"
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