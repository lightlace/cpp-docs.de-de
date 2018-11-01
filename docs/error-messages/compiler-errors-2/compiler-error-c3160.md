---
title: Compilerfehler C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 96fd97aa5021b7e1bc5226162f9c54ff4d6211b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649743"
---
# <a name="compiler-error-c3160"></a>Compilerfehler C3160

„Zeiger“: Ein Datenmember einer verwalteten oder WinRT-Klasse kann nicht diesen Typ aufweisen.

Innere Garbage Collection-Zeiger können auf das Innere einer verwalteten oder WinRT-Klasse verweisen. Da diese langsamer als Zeiger auf gesamte Objekte sind und eine besondere Behandlung durch den Garbage Collector erfordern, können innere verwaltete Zeiger nicht als Member einer Klasse deklariert werden.

Im folgenden Beispiel wird C3160 generiert:

```
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
