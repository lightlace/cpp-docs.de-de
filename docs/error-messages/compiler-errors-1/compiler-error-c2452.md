---
title: Compilerfehler C2452 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2452
dev_langs:
- C++
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c8785a8ce77849805d9620b412493accd8b8690
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087005"
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