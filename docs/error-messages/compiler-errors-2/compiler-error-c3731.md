---
title: Compilerfehler C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 9acf80eec0d36db64fa070d691533e7085754ac0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752950"
---
# <a name="compiler-error-c3731"></a>Compilerfehler C3731

Inkompatibles Ereignis "Funktion1" und Handler "Funktion2"; Ereignis Quelle und Ereignishandler müssen denselben Typ aufweisen.

Die Ereignis Quelle und der Ereignis Empfänger müssen denselben Typ aufweisen (z. b. `native` im Vergleich zu `com` Typen). Um diesen Fehler zu beheben, nehmen Sie die Typen der Ereignis Quelle und des Ereignis Handlers in Einklang.

Im folgenden Beispiel wird C3731 generiert:

```cpp
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```
