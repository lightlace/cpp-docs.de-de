---
title: Compilerfehler C2600
ms.date: 11/04/2016
f1_keywords:
- C2600
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
ms.openlocfilehash: b2d95460cadf03f9152599ef47ae703030326dd1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740740"
---
# <a name="compiler-error-c2600"></a>Compilerfehler C2600

'Funktion': kann keine vom Compiler generierte spezielle Memberfunktion definieren (Deklaration in der ersten Klasse erforderlich)

Bevor Sie Member-Funktionen wie Konstruktoren oder Destruktoren für eine Klasse definieren können, müssen sie in der Klasse deklariert werden. Der Compiler kann standardmäßige Konstruktoren und Destruktoren (speziellen Memberfunktionen genannt) generieren, wenn keine in der Klasse deklariert werden. Wenn Sie eine dieser Funktionen ohne eine entsprechende Deklaration in der Klasse definieren, erkennt der Compiler jedoch einen Konflikt.

Beheben Sie diesen Fehler, indem Sie in der Klassendeklaration jede Member-Funktion, die Sie außerhalb der Klassendeklaration definieren, deklarieren.

Im folgenden Beispiel wird C2600 generiert:

```cpp
// C2600.cpp
// compile with: /c
class C {};
C::~C() {}   // C2600

class D {
   D::~D();
};

D::~D() {}
```
