---
title: Compilerfehler C3651
ms.date: 11/04/2016
f1_keywords:
- C3651
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
ms.openlocfilehash: 5601dd2f510e4322e67f49478eefce795312e380
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494178"
---
# <a name="compiler-error-c3651"></a>Compilerfehler C3651

'Member': kann nicht als explizite Überschreibung verwendet werden, muss ein Member einer Basisklasse sein

Eine explizite Überschreibung wurde angegeben, aber die überschriebene Funktion wurde in einem Typ, der nicht der Basistyp ist.

Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3651 generiert:

```
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