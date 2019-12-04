---
title: Compilerfehler C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 76cc35e57c1577ed23c043740f37c602600da542
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748501"
---
# <a name="compiler-error-c2589"></a>Compilerfehler C2589

"Identifier": Ungültiges Token auf der rechten Seite von "::"

Wenn auf der linken Seite des Bereichs Auflösungs Operators (Doppelpunkte) ein Klassen-, Struktur-oder Union-Name angezeigt wird, muss das Token auf der rechten Seite ein Klassen-, Struktur-oder Union-Member sein. Andernfalls kann ein beliebiger globaler Bezeichner auf der rechten Seite angezeigt werden.

Der Bereichs Auflösungs Operator kann nicht überladen werden.

Im folgenden Beispiel wird C2589 generiert:

```cpp
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```
