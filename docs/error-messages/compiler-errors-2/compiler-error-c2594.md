---
title: Compilerfehler C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: ade657f9ada2a2249d2f96b7caada7b9719195d1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759333"
---
# <a name="compiler-error-c2594"></a>Compilerfehler C2594

' Operator ': mehrdeutige Konvertierungen von ' Typ1 ' in ' Typ2 '

Keine Konvertierung von *Typ1* in *Typ2* war direkter als jede andere. Wir empfehlen zwei mögliche Lösungen für die Umstellung von *Typ1* auf *Typ2*. Die erste Option besteht darin, eine direkte Konvertierung von *Typ1* zu *Typ2*zu definieren. die zweite Option besteht darin, eine Sequenz von Konvertierungen von *Typ1* in *Typ2*anzugeben.

Im folgenden Beispiel wird C2594 generiert. Die vorgeschlagene Lösung für den Fehler ist eine Sequenz von Konvertierungen:

```cpp
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```
