---
title: Compilerfehler C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 18d8f7130c34f5e1e33bc7aa9b9463f50c243045
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386940"
---
# <a name="compiler-error-c2589"></a>Compilerfehler C2589

'Bezeichner': Ungültiges Token auf der rechten Seite des '::'

Wenn eine Klasse, Struktur oder union-Namen auf der linken Seite des Bereichsauflösungsoperators (zwei Doppelpunkte) angezeigt wird, muss das Token auf der rechten Seite eine Klasse, Struktur oder union-Member sein. Andernfalls kann alle globaler Bezeichner auf der rechten Seite angezeigt.

Der Bereichsauflösungsoperator kann nicht überladen werden.

Im folgende Beispiel wird die C2589 generiert:

```
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```