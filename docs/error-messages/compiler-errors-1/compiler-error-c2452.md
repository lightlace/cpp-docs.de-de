---
title: Compilerfehler C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 3e2d583efa2b634cf49d8588fa398bd81f24c607
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781106"
---
# <a name="compiler-error-c2452"></a>Compilerfehler C2452

'Typ': Ungültiger Quelltyp für Safe_cast

Der Quelltyp für ["safe_cast"](../../extensions/safe-cast-cpp-component-extensions.md) war ungültig.  Z. B. alle Typen in einem `safe_cast` Vorgang muss die CLR-Typen.

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