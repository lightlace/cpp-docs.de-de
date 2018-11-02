---
title: Compilerfehler C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: a6084632ac0a84cc058ea73eb3c2b632208792eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475932"
---
# <a name="compiler-error-c3612"></a>Compilerfehler C3612

'Typ': eine versiegelte Klasse darf nicht abstrakt sein

Mithilfe von definierten Typen `value` sind standardmäßig versiegelt und eine Klasse ist abstrakt, es sei denn, sie alle Methoden der Basisklasse implementiert. Eine versiegelte abstrakte Klasse kann weder eine Basisklasse sein, noch kann er instanziiert werden.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).

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