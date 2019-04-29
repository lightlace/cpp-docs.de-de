---
title: Compilerfehler C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 3f3fac9d5410595fe5653e257d97d2fd7c858545
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303488"
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

Es ist möglich, einen Zeiger auf einen Typ deklariert, aber nicht definierte zu deklarieren.  Visual C++, nicht jedoch einen Verweis auf einen nicht definierten Typ.

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