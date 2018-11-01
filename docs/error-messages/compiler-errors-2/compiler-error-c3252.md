---
title: Compilerfehler C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: ee9245fb8eb89b9234e76dc10304b1d05bc1fdcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600381"
---
# <a name="compiler-error-c3252"></a>Compilerfehler C3252

"Methode" : Der Zugriff auf eine virtuelle Methode kann in einem verwaltetem oder WinRT-Typ nicht reduziert werden.

Eine Klasse, die eine virtuelle Methode von einer Basisklasse oder eine Methode implementiert, kann den Zugriff auf diese Methode nicht reduzieren.

Beachten Sie, dass alle Methoden in einer Schnittstelle öffentlich sind.

Im folgenden Beispiel wird C3252 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```