---
title: Compilerfehler C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 5acc33869648f83cd44bc557128c685f521ddf88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496056"
---
# <a name="compiler-error-c3731"></a>Compilerfehler C3731

Inkompatibles Ereignis "Funktion1" und der Handler "Funktion2"; Ereignisquelle und Ereignishandler müssen vom gleichen Typ sein.

Die Ereignisquelle und einen Ereignisempfänger müssen denselben Typ haben (z. B. `native` im Vergleich zu `com` Typen). Um diesen Fehler zu beheben, stellen Sie die Typen von der Ereignisquelle und Ereignishandler.

Im folgende Beispiel wird die C3731 generiert:

```
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