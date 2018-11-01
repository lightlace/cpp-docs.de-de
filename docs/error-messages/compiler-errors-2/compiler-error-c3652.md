---
title: Compilerfehler C3652
ms.date: 11/04/2016
f1_keywords:
- C3652
helpviewer_keywords:
- C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
ms.openlocfilehash: acdb8f7687639e2b35e36ea9ebf514292f4631fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470329"
---
# <a name="compiler-error-c3652"></a>Compilerfehler C3652

"override": eine Funktion, die explizite überschreibungen durchführt, muss virtuell sein

Eine Funktion, die eine explizite Überschreibung muss virtuell sein. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3652 generiert:

```
// C3652.cpp
// compile with: /clr /c
public interface class I {
   void f();
};

public ref struct R : I {
   void f() = I::f {}   // C3652
   // try the following line instead
   // virtual void f() = I::f {}
};
```