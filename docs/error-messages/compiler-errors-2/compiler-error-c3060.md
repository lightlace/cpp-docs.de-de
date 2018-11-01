---
title: Compilerfehler C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: c77af7fa1220aa5211d480cddf3bf0979c642ade
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515400"
---
# <a name="compiler-error-c3060"></a>Compilerfehler C3060

'Member': Eine Friend-Funktion kann nicht mit einem qualifizierten Namen innerhalb einer Klasse definiert werden (sie kann nur deklariert werden).

Eine Friend-Funktion wurde mit einem qualifizierten Namen definiert. Das ist nicht zulässig.

Im folgenden Beispiel wird C3060 generiert:

```
// C3060.cpp
class A {
public:
   void func();
};

class C {
public:
   friend void A::func() { }   // C3060
   // Try the following line and the out of class definition:
   // friend void A::func();
};

// void A::func(){}
```