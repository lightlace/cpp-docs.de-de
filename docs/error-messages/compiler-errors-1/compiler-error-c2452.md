---
title: Compilerfehler C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 7e8173c2697a931e5b292dc974b6d1b22f376794
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744107"
---
# <a name="compiler-error-c2452"></a>Compilerfehler C2452

' Typ ': Ungültiger Quelltyp für safe_cast

Der Quelltyp für [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) war ungültig.  Beispielsweise müssen alle Typen in einer `safe_cast` Operation CLR-Typen sein.

Im folgenden Beispiel wird C2452 generiert:

```cpp
// C2452.cpp
// compile with: /clr

struct A {};
struct B : public A {};

ref struct C {};
ref struct D : public C{};

int main() {
   A a;
   safe_cast<B*>(&a);   // C2452

   // OK
   C ^ c = gcnew C;
   safe_cast<D^>(c);
}
```
