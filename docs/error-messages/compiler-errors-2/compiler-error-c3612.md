---
title: Compilerfehler C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 499c31b0c02bd72695cd6118612609a70316f0ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755745"
---
# <a name="compiler-error-c3612"></a>Compilerfehler C3612

' Typ ': eine versiegelte Klasse kann nicht abstrakt sein.

Typen, die mit `value` definiert sind, sind standardmäßig versiegelt, und eine Klasse ist abstrakt, es sei denn, Sie implementiert alle Methoden der Basis. Eine versiegelte abstrakte Klasse kann keine Basisklasse sein und kann nicht instanziiert werden.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3612 generiert:

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
