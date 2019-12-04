---
title: Compilerfehler C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d0e283c7cd6116655a56f8df67ab4eecf9923b68
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760940"
---
# <a name="compiler-error-c2884"></a>Compilerfehler C2884

"Name": wird mit der-Deklaration in Konflikt mit der lokalen Funktion "Function" eingeführt.

Sie haben versucht, eine Funktion mehrmals zu definieren. Die erste Definition ist eine lokale Definition. Die zweite ist von einem Namespace mit einer `using` Deklaration.

Im folgenden Beispiel wird C2884 generiert:

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
