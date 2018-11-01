---
title: Compilerfehler C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: 75e3b438dd69f8879fdc2273a8f0357229941340
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428284"
---
# <a name="compiler-error-c2594"></a>Compilerfehler C2594

'Operator': Mehrdeutige Konvertierung von 'type1' in 'Typ2'

Keine Konvertierung von *type1* zu *Typ2* war als alle anderen direkter. Sollten zwei mögliche Lösungen zum Konvertieren von *type1* zu *Typ2*. Die erste Möglichkeit besteht, definieren Sie eine direkte Konvertierung von *type1* zu *Typ2*, und die zweite Option zur Angabe einer Abfolge von Konvertierungen von *type1* zu  *Typ2*.

Im folgende Beispiel wird die C2594 generiert. Die vorgeschlagene Lösung an den Fehler ist eine Sequenz von Konvertierungen:

```
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