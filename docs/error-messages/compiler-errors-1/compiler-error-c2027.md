---
title: Compilerfehler C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 901e9b791616c5684b352c1fda7687f67b895d9c
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447376"
---
# <a name="compiler-error-c2027"></a>Compilerfehler C2027

Verwendung von undefiniertem Typ 'Typ'

Ein Typ kann nicht verwendet werden, bevor sie definiert ist. Um den Fehler zu beheben, achten Sie darauf, dass der Typ vollständig definiert ist, bevor auf Sie verwiesen wird.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2027 generiert.

```
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>Beispiel

Es ist möglich, einen Zeiger auf einen Typ deklariert, aber nicht definierte zu deklarieren. Aber C++ lässt sich nicht auf einen Verweis auf einen nicht definierten Typ.

Im folgende Beispiel wird die C2027 generiert.

```
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```