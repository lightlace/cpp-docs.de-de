---
title: Compilerfehler C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 48d0fef86908f3ba5a547417d0625febc5226454
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752703"
---
# <a name="compiler-error-c3739"></a>Compilerfehler C3739

"Class": die Syntax wird nur unterstützt, wenn der Parameter "layout_dependent" event_receiver "true" ist.

Sie haben versucht, eine gesamte Ereignis Schnittstelle zu verbinden, `layout_dependent` auf [event_receiver](../../windows/event-receiver.md) Attribut jedoch nicht "true" ist. Sie müssen jeweils ein einzelnes Ereignis anschließen.

Im folgenden Beispiel wird C3739 generiert:

```cpp
// C3739.cpp
struct A
{
   __event void e();
};

// event_receiver is implied
// [ event_receiver(layout_dependent=false)]

// use the following line instead
// [event_receiver(com, layout_dependent=true), coclass ]
struct B
{
   void f();
   B(A* a)
   {
      __hook(A, a, &B::f);   // C3739
      // use the following line instead to hook a single event
      // __hook(&A::e, a, &B::f);
   }
};

int main()
{
}
```
