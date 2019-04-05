---
title: Compilerfehler C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: ab18381d3f263e3207662e1667ac5c835983412f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781405"
---
# <a name="compiler-error-c3612"></a>Compilerfehler C3612

'Typ': eine versiegelte Klasse darf nicht abstrakt sein

Mithilfe von definierten Typen `value` sind standardmäßig versiegelt und eine Klasse ist abstrakt, es sei denn, sie alle Methoden der Basisklasse implementiert. Eine versiegelte abstrakte Klasse kann weder eine Basisklasse sein, noch kann er instanziiert werden.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3612 generiert:

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```