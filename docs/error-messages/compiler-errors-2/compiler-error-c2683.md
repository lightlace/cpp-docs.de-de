---
title: Compilerfehler C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 8526dc1fe3cacc872aa91ca058677d15318fd703
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760269"
---
# <a name="compiler-error-c2683"></a>Compilerfehler C2683

' Cast ': ' type ' ist kein polymorpher Typ.

Sie können [dynamic_cast](../../cpp/dynamic-cast-operator.md) nicht verwenden, um eine nicht-polymorphe Klasse (eine Klasse ohne virtuelle Funktionen) zu konvertieren.

Sie können [static_cast](../../cpp/static-cast-operator.md) verwenden, um Konvertierungen von nicht polymorphen Typen auszuführen. `static_cast` führt jedoch keine Lauf Zeit Überprüfung durch.

Im folgenden Beispiel wird C2683 generiert:

```cpp
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```
