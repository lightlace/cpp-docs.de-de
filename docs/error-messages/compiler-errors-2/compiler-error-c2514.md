---
title: Compilerfehler C2514
ms.date: 11/04/2016
f1_keywords:
- C2514
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
ms.openlocfilehash: aef9df0718d013378f88c1a34d08d1b1e05e214c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667003"
---
# <a name="compiler-error-c2514"></a>Compilerfehler C2514

'Klasse': Klasse besitzt keine Konstruktoren

Die Klasse, Struktur oder Union verfügt über keinen Konstruktor mit einer Parameterliste, die den Parametern, die instanziiert wird, entspricht.

Eine Klasse muss vollständig deklariert werden, bevor es instanziiert werden kann.

Im folgende Beispiel wird die C2514 generiert:

```
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```