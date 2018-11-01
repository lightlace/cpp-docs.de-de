---
title: Compilerfehler C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: d3acfd9d4d09c53fac0b2c5a2462c56dfd54e6d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598548"
---
# <a name="compiler-error-c3670"></a>Compilerfehler C3670

"override": kann nicht zugegriffen werden Basisklassenmethode 'Methode' kann nicht überschrieben werden

Eine Außerkraftsetzung kann nur auf eine Funktion stattfinden, deren Zugriffsebene, die es in einem abgeleiteten Typ zur Verfügung stellt. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3670 generiert:

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```