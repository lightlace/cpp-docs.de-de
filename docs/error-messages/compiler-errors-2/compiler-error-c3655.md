---
title: Compilerfehler C3655
ms.date: 11/04/2016
f1_keywords:
- C3655
helpviewer_keywords:
- C3655
ms.assetid: 724919ab-2915-4b61-8794-44648e162d62
ms.openlocfilehash: 61762612cf5b2153319435532dca100eb77c274d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756304"
---
# <a name="compiler-error-c3655"></a>Compilerfehler C3655

"Funktion": die Funktion wurde bereits explizit überschrieben.

Eine Funktion kann nur einmal explizit überschrieben werden. Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

Im folgenden Beispiel wird C3655 generiert:

```cpp
// C3655.cpp
// compile with: /clr /c
public ref struct B {
   virtual void f();
   virtual void g();
};

public ref struct D : B {
   virtual void f() new sealed = B::f;
   virtual void g() new sealed = B::f;   // C3655
   // try the following line instead
   // virtual void g() new sealed = B::g;
};
```
