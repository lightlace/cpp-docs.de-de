---
title: Compilerfehler C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378868"
---
# <a name="compiler-error-c2883"></a>Compilerfehler C2883

"Name": Funktionsdeklaration steht in Konflikt mit "Bezeichner" eingeführt, durch eine using-Deklaration

Sie haben versucht, eine Funktion mehr als einmal definiert. Die erste Definition wurde aus einem Namespace mit einem `using` Deklaration. Bei der zweiten handelte es sich um eine lokale Definition.

Im folgende Beispiel wird die C2883 generiert:

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```