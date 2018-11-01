---
title: Compilerfehler C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 49e4897ad5db866aa1ca42589859bedff12718df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625155"
---
# <a name="compiler-error-c2683"></a>Compilerfehler C2683

'cast': 'Typ' ist kein polymorpher Typ

Sie können keine [Dynamic_cast](../../cpp/dynamic-cast-operator.md) aus einer nicht polymorph-Klasse (eine Klasse ohne virtuelle Funktionen) zu konvertieren.

Sie können ["static_cast"](../../cpp/static-cast-operator.md) zum Durchführen von Konvertierungen von nicht polymorphen Typen. Allerdings `static_cast` führt eine laufzeitüberprüfung nicht aus.

Im folgende Beispiel wird die C2683 generiert:

```
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```