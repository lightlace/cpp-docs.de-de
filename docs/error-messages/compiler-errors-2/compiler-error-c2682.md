---
title: Compilerfehler C2682
ms.date: 11/04/2016
f1_keywords:
- C2682
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
ms.openlocfilehash: 8a9ec2f59f362df284e9bd5cd8df6ae986d59d77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439415"
---
# <a name="compiler-error-c2682"></a>Compilerfehler C2682

casting_operator kann nicht von 'type1' in 'type2' konvertieren

Ein Umwandlungsoperator versucht für die Konvertierung zwischen inkompatiblen Typen. Beispielsweise können keine der [Dynamic_cast](../../cpp/dynamic-cast-operator.md) Operator, um einen Zeiger auf einen Verweis zu konvertieren. Die `dynamic_cast` Operator kann nicht zum Umwandeln von Qualifizierer verwendet werden. Alle Qualifizierer für die Typen müssen übereinstimmen.

Sie können die `const_cast` Operator, um das Entfernen von Attributen wie z. B. `const`, `volatile`, oder `__unaligned`.

Im folgende Beispiel wird die C2682 generiert:

```
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

Im folgende Beispiel wird die C2682 generiert:

```
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```