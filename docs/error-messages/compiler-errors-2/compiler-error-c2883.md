---
title: Compilerfehler C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: cb6b1043d976cfeb8cb92c8780c5b84ea9700b8b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760953"
---
# <a name="compiler-error-c2883"></a>Compilerfehler C2883

"Name": die Funktionsdeklaration steht in Konflikt mit "Identifier", die mit der using-Deklaration

Sie haben versucht, eine Funktion mehrmals zu definieren. Die erste Definition wurde aus einem Namespace mit einer `using` Deklaration erstellt. Die zweite war eine lokale Definition.

Im folgenden Beispiel wird C2883 generiert:

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
