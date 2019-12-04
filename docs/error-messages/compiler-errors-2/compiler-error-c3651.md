---
title: Compilerfehler C3651
ms.date: 11/04/2016
f1_keywords:
- C3651
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
ms.openlocfilehash: 9468b1e9193bfa52ed133f6fdfa398e02e40c4ef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756317"
---
# <a name="compiler-error-c3651"></a>Compilerfehler C3651

"Member": kann nicht als explizite Überschreibung verwendet werden, muss ein Member einer Basisklasse sein.

Es wurde eine explizite außer Kraft Setzung angegeben, aber die überschriebene Funktion war in einem Typ, der kein Basistyp ist.

Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

Im folgenden Beispiel wird C3651 generiert:

```cpp
// C3651.cpp
// compile with: /clr /c
ref class C {
public:
   virtual void func2();
};

ref class Other {
public:
   virtual void func();
};

ref class D : public C {
public:
   virtual void func() new sealed = Other::func;   // C3651
   virtual void func2() new sealed = C::func2;   // OK
};
```
