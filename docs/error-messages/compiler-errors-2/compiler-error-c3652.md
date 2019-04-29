---
title: Compilerfehler C3652
ms.date: 11/04/2016
f1_keywords:
- C3652
helpviewer_keywords:
- C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
ms.openlocfilehash: 350edcf409cf2a890a8f83147ce0ae13e9992694
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385562"
---
# <a name="compiler-error-c3652"></a>Compilerfehler C3652

"override": eine Funktion, die explizite überschreibungen durchführt, muss virtuell sein

Eine Funktion, die eine explizite Überschreibung muss virtuell sein. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md).

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