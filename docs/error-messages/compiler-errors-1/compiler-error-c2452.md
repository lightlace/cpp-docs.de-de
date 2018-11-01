---
title: Compilerfehler C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 9b9f2c41da1eb36aceece7f14ad5c33b38404bb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523698"
---
# <a name="compiler-error-c2452"></a>Compilerfehler C2452

'Typ': Ungültiger Quelltyp für Safe_cast

Der Quelltyp für ["safe_cast"](../../windows/safe-cast-cpp-component-extensions.md) war ungültig.  Z. B. alle Typen in einem `safe_cast` Vorgang muss die CLR-Typen.

Im folgende Beispiel wird die C2452 generiert:

```
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